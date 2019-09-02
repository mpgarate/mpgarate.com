# Michael Garate
I'm a **Software Engineer** currently at **Etsy** working on **Machine Learning Infrastructure**.

## Contact
- [michael@garate.email](mailto:michael@garate.email)
- [LinkedIn](http://linkedin.com/in/mpgarate/)
- [GitHub](https://github.com/mpgarate)

## Resume
- [Resume](https://docs.google.com/document/d/1MXwxtcTSsGAPKCYOreMZ3lpVVDFdWO_2-o7R80zpNzc/edit?usp=sharing)

## Open Source
### fastText vector export optimization
Etsy uses [fastText](https://github.com/facebookresearch/fastText/) to generate word vectors for a variety of ML applications. [This code change](https://github.com/facebookresearch/fastText/pull/843) allows fastText to serialize floating point values using multiple cores, which reduced the runtime of many Etsy workloads from hours to minutes.
