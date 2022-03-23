---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Michael Garate
---

## Blog

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}" alt="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## On the Web 🏄

### (music) Post-classical Piano EP "Shamrock"

"Shamrock" is a collection of piano improvisations with touches of electronic and orchestral elements. It is available on [Spotify](https://open.spotify.com/album/3qFIB2qmz8X1EglbzMMT20?si=XpWU86nyQKyHOm4E-8Md3Q), [Bandcamp](https://michaelgarate.bandcamp.com/album/shamrock?from=embed), and [other streaming apps](https://album.link/6snfns0vcvxtg). The recordings feature relaxed meter, meditative soundscapes, and hopeful melodies. Influences include Goldmund, Balmorhea, Nils Frahm, Sophie Hutchings, and Air.


### (article) Distributed Firewall for Network security at LinkedIn
LinkedIn uses [iptables](https://en.wikipedia.org/wiki/Iptables) to enforce firewall rules on over 300k hosts. [This article](https://engineering.linkedin.com/blog/2021/distributed-firewall-network-security) describes the client-server architecture that makes it possible to distribute and monitor the rules at scale.

### (code) Optimizing fastText vector exports
Etsy uses [fastText](https://github.com/facebookresearch/fastText/) to generate word vectors for a variety of ML applications. [This optimization](https://github.com/facebookresearch/fastText/pull/843) allows fastText to serialize floating point values using multiple cores, which reduced the runtime of many Etsy workloads from hours to minutes.
