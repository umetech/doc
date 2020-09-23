# Inside the Google Translate Api

# Portal Api Uri

- `https://translate.googleapis.com/translate_a/`
- `https://translate.google.com/translate_a/`
- `https://clients5.google.com/translate_a/`
- `https://translate.google.so/translate_a/`

the first argument after the `translate_a/`: either `single` or `t`

# Parameters

- `client` -  'gtx', 't' or 'dict-chrome-ex'
- `sl` - source language code (`auto` for autodetection)
- `tl` - translation language
- `q` - source text / word, what you type in the search box
- `hl` - sk //language of the interface (default:en, you can try xx-bork or xx-hacker)
  dt:bd
  dt:ex
  dt:ld
  dt:md
  dt:qc
  dt:rw
  dt:rm
  dt:ss
  dt:t
  dt:at
  dt:sw
  ie:UTF-8 // encoding of the input (default: utf-8)
  oe:UTF-8 // encoding of the output, the results (default: utf-8)
  otf:1
  srcrom:1
  ssel:3
  tsel:0

# Examples

- https://clients5.google.com/translate_a/t?client=dict-chrome-ex&sl=en&tl=zh&dt=t&q=shoe
- https://translate.googleapis.com/translate_a/single?client=gtx&sl=en&tl=zh&dt=t&q=shoe&ie=UTF-8&oe=UTF-8&dj=1


# References

- https://stackoverflow.com/questions/57397073/difference-between-the-google-translate-api
- https://stackoverflow.com/questions/43155233/google-translate-api-paid-vs-google-translate-api-free
- https://stackoverflow.com/questions/26714426/what-is-the-meaning-of-google-translate-query-params/29537590#29537590
- https://support.google.com/translate/?hl=en#topic=7011755
- https://en.wikipedia.org/wiki/Google_Translate

