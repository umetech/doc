# Inside the Google Translate Api

# Portal Api Uri

- `https://translate.googleapis.com/translate_a/`
- `https://translate.google.com/translate_a/`
- `https://clients5.google.com/translate_a/`
- `https://translate.google.so/translate_a/`

the first argument after the `translate_a/`: either `single` or `t`

# Parameters

- `client` -  'gtx', 't' or 'dict-chrome-ex', 'webapp'

> 't' probably represents the standalone google translate web app (as opposed to a mobile app, or the widget that pops up if you google search "translate")

- `sl` - source language code (`auto` for autodetection)
- `tl` - translate target language code
- `q` - source text / word, what you type in the search box
- `ie` - encoding of the input (default: utf-8)
- `oe` - encoding of the output, the results (default: utf-8)
- `dt` - may be included more than once and specifies what to return in the reply.

    **Here are some values for dt. If the value is set, the following data will be returned**

  > at - alternate translations
  > bd - dictionary, in case source text is one word (you get translations with articles, reverse translations, etc.)
  > dj - Json response with names. (dj=1)
  > ex - examples
  > ld - 
  > md - definitions of source text, if it's one word
  > qc - 
  > rm - transcription / transliteration of source and translated texts
  > rw - See also list
  > ss - synonyms of source text, if it's one word
  > sw - 
  > t - translation of source text

- `hl` - sk //language of the interface (default:en, you can try xx-bork or xx-hacker)
- `otf` - 1
- `srcrom` - 1, seems to be present when the source text has no spelling suggestions
- `ssel` - 3
- `tsel` - 0

# Examples

- https://clients5.google.com/translate_a/t?client=dict-chrome-ex&sl=en&tl=zh&dt=t&q=shoe
- https://translate.googleapis.com/translate_a/single?client=gtx&sl=en&tl=zh&dt=t&q=shoe&ie=UTF-8&oe=UTF-8&dj=1


# References

- https://stackoverflow.com/questions/57397073/difference-between-the-google-translate-api
- https://stackoverflow.com/questions/43155233/google-translate-api-paid-vs-google-translate-api-free
- https://stackoverflow.com/questions/26714426/what-is-the-meaning-of-google-translate-query-params/29537590#29537590
- https://support.google.com/translate/?hl=en#topic=7011755
- https://en.wikipedia.org/wiki/Google_Translate

