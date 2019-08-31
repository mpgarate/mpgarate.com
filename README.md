# Michael Garate
michael@garate.email

Senior Software Engineer at Etsy on Machine Learning Infrastructure

## Projects
### fastText vector export optimization
Etsy uses [fastText](https://github.com/facebookresearch/fastText/) to generate word vectors for a variety of ML applications. [This code change](https://github.com/facebookresearch/fastText/pull/843) allows fastText to serialize floating point values using multiple cores, which reduced the runtime of many Etsy workloads from hours to minutes.
