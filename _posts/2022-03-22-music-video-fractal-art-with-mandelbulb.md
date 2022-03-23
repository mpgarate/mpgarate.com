---
layout: post
title:  "Music Video Fractal Art with Mandelbulb"
date:   2022-03-22
---

I wanted "Jade" to have a video that was both meditative and electrifying. Fractal animation brought that dream to life. Please enjoy the music video!

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/GlMZtZ7Ji7c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The full EP is available on <a href="https://open.spotify.com/album/3qFIB2qmz8X1EglbzMMT20?si=XpWU86nyQKyHOm4E-8Md3Q" target="_blank">Spotify</a> and <a href="https://album.link/6snfns0vcvxtg" target="_blank">other streaming apps</a>. For more about the music, see [this post]({% post_url 2022-03-17-introducing-shamrock-ep %}).

This video is possible thanks to the wonderful [Mandelbulb3d project](https://www.mandelbulb.com/2014/mandelbulb-3d-mb3d-fractal-rendering-software/). Of all the mandelbulb animation software I tested, mb3d gave the best quality results and a huge amount of controls. This post describes the video creation process.

## 1. Creating a shape

<a href="/assets/music/video-fractal-post/mandelbulb3d-animation-export.jpg" target="_blank"><img width="512px" alt="" src="/assets/music/video-fractal-post/mandelbulb3d-animation-export.jpg" /></a>

The shape comes from 5 formulas working together in an alternating fashion. The earlier the function is in this list, the greater its effect on the object. mb3d provides dozens of functions to explore.

1. First we apply `sin` to the y axis. This creates a smooth infinite repetition of the overall shape. Without this, the object would roughly resemble a sphere or box.
2. Next, we apply `MengerKoch` to give large scale features of the shape.
3. `AmazingBox2` gives a lot of the "feel" of the surface textures and the medium size details. This is what gives it the boxy "space station" vibe.
4. `ReciprocalZ3b` transforms the Z axis by computing its reciprocal. It adds a lot of variety to the object. Without it, there is more symmetry and closely nested boxes.
5. `Sierpinski4` gives a moderate curvature and additional surface detail.

Each of the above functions has 3-8 tunable parameters, and a small adjustment to any one of them can have a dramatic effect. It is a delicate balance to fine-tune a shape without diving into total chaos.

With the shape in place, we can choose an interesting starting position for the camera. This animation shows zooming from the full object view, down into the object, and aiming directly at the y axis to reach the starting keyframe.

<img width="512px" alt="Zooming the camera to an interesting part of the fractal" src="/assets/music/video-fractal-post/zoom.gif" />

Performing a 360 degree rotation from the starting position. If the camera is too close to an object, it can produce stretch marks.

<img width="512px" alt="360 degree rotation from the starting position" src="/assets/music/video-fractal-post/spin.gif" />

We also apply some extra lighting to give depth. This gif animates turning on and off a custom light. There is also a custom mapping for the background and surface colors.

<img width="512px" alt="Turning on and off lighting on the object" src="/assets/music/video-fractal-post/light.gif" />

## 2. Animation

To make it move, we modulate two fractal parameters over time.

### Moving the camera through the shape
Since the `sin` formula repeats the object on the Y axis and the camera directly faces the Y axis, modulating the `sin` offset parameter between `0` and `π` creates the effect of moving the camera through the shape until seamlessly reaching the starting point again. Note that if the camera hits an object, we get blown out artifacts. In the end result, we should avoid this.

<img width="512px" alt="Animating moving the camera on the y axis" src="/assets/music/video-fractal-post/loop-sin-offset-only.gif" />

### Making the object breathe
`MengerKoch` offers a `CScaleY` parameter that gradually moves large parts of the object relative to each other. After experimenting with many different params, I chose this one to add some motion to the object itself while the camera flies through. Since this value is not naturally looping like the `sin` function, the value "breathes" up from value `a` to `b` and back down to `a`. I would have preferred a cyclical, naturally looping value similar to `sin`, however all of the ones I tried changed the shape too dramatically. Maybe I will have better luck in a future video.

<img width="512px" alt="Animating moving the object so that it 'breathes'" src="/assets/music/video-fractal-post/loop-menger-koch-csale-y-only.gif" />


Mandelbulb supports modulation using keyframes. This loop used the following 3 frames.

<img width="256px" alt="Keyframe 1" src="/assets/music/video-fractal-post/keyframe_1.jpg" />
<img width="256px" alt="Keyframe 2" src="/assets/music/video-fractal-post/keyframe_2.jpg" />
<img width="256px" alt="Keyframe 3" src="/assets/music/video-fractal-post/keyframe_3.jpg" />

We can summarize the change between them as follows.

```yaml
- frame_1:
    sin_y:
      offset_1: 0
    menger_koch:
      cscale_y: 1.05
- frame_2:
    sin_y:
      offset_1: 1.57080
    menger_koch:
      cscale_y: 0.875
- frame_3:
    sin_y:
      offset_1: 3.14159
    menger_koch:
      cscale_y: 1.05
```

<img width="512px" alt="Full loop preview" src="/assets/music/video-fractal-post/loop-full.gif" />

It took about 6 days for my home PC to render 1700 frames at 1440p (with 2x upscaling for antialiasing).

Next, I manually touched up a few images that had blown out highlights and sent all of the images through [Flowframes](https://nmkd.itch.io/flowframes) to quadruple the framerate using RIFE (NCNN) for interpolation. The result was a nearly 2 minute video at 60fps that could seamlessly loop from start to end.

## 4. Final Touches

Several effects bring the fractal into a more abstract space.

The Adobe After Effects effect "CC Kaleida" wraps the image geometrically in a Kaleidoscope style. We modulate the size, rotation angle, and opacity of the effect along with the music.

We use "Colorama" to rotate the hue based on the formula `(time * 5) % 360`, and a custom opacity param allows ramping it up and down following the music.

You may also notice a few layers of snow/dust sprinkled in.


<img width="100%" alt="" src="/assets/music/video-fractal-post/jade-final-still.jpg" />

## Credits

Thank you to Julius Horsthuis for the [video tutorial](https://www.youtube.com/watch?v=15XYMlH-0JU) and [inspirational portfolio](http://www.julius-horsthuis.com/). Really beautiful artwork.
