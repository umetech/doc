# Inside the Google Translate Api

# Portal Api Uri

- `https://translate.googleapis.com/translate_a/`
- `https://translate.google.com/translate_a/`
- `https://clients5.google.com/translate_a/`
- `https://translate.google.so/translate_a/`
- `https://translate.google.cn/translate_a/`

the first argument after the `translate_a/`: either `single` or `t`

# Parameters

- `client` -  'gtx', 't', 'j', 'p', 'dict-chrome-ex', 'webapp'

> 't' probably represents the standalone google translate web app (as opposed to a mobile app, or the widget that pops up if you google search "translate")

- `sl` - source language code (`auto` for autodetection)
- `tl` - translate target language code
- `q` - source text / word, what you type in the search box
- `ie` - encoding of the input (default: utf-8)
- `oe` - encoding of the output, the results (default: utf-8)
- `dt` - may be included more than once and specifies what to return in the reply.

    **Here are some values for dt. If the value is set, the following data will be returned**

  > at - Alternate or other translations (in google translate page this shows when click on translated word)
  > bd - Full translate with synonym, dictionary, in case source text is one word (you get translations with articles, reverse translations, etc.)
  > dj - Json response with names. (dj=1)
  > ex - Examples
  > ld - Unknown
  > md - Definitions part with example, if it's one word
  > qc - 
  > qca - 
  > rm - transcription / transliteration of source and translated texts
  > rw - See also list
  > ss - Full synonyms of source text, if it's one word
  > sw - 
  > t - translation of source text


- `hl` - 'en', language of the interface (default:en, you can try xx-bork or xx-hacker)
- `kc` -1,
- `multires` - 1,
- `otf` - 1,
- `pc` - 1,
- `srcrom` - 1, seems to be present when the source text has no spelling suggestions
- `sc` - 1,
- `ssel` - 3,
- `tk` - token
- `trs` -1,
- `tsel` - 0,

- `total` -,
- `idx` - 0,
- `textlen` -,
- `prev` - 'input'

# Examples

- https://clients5.google.com/translate_a/t?client=dict-chrome-ex&sl=en&tl=zh&dt=t&q=shoe
- https://translate.googleapis.com/translate_a/single?client=gtx&sl=en&tl=zh&dt=t&q=shoe&ie=UTF-8&oe=UTF-8&dj=1
- https://translate.google.com/translate_a/single?client=gtx&dj=1&sl=en&tl=zh&hl=en&dt=bd&dt=ex&dt=ld&dt=md&dt=qca&dt=rw&dt=rm&dt=ss&dt=t&dt=at&ie=UTF-8&oe=UTF-8&otf=1&ssel=0&tsel=0&kc=1&tk=685532.807248&q=shoe


# References

- https://stackoverflow.com/questions/57397073/difference-between-the-google-translate-api
- https://stackoverflow.com/questions/43155233/google-translate-api-paid-vs-google-translate-api-free
- https://stackoverflow.com/questions/26714426/what-is-the-meaning-of-google-translate-query-params/29537590#29537590
- https://support.google.com/translate/?hl=en#topic=7011755
- https://en.wikipedia.org/wiki/Google_Translate
- https://github.com/Stichoza/google-translate-php/blob/master/src/GoogleTranslate.php
- https://github.com/matheuss/google-translate-token
- https://github.com/matheuss/google-translate-api


```javascript
return token.get(text).then(function (token) {
        var url = 'https://translate.google.com/translate_a/single';
        var data = {
            client: 't',
            sl: opts.from,
            tl: opts.to,
            hl: opts.to,
            dt: ['at', 'bd', 'ex', 'ld', 'md', 'qca', 'rw', 'rm', 'ss', 't'],
            ie: 'UTF-8',
            oe: 'UTF-8',
            otf: 1,
            ssel: 0,
            tsel: 0,
            kc: 7,
            q: text
        };
        data[token.name] = token.value;

        return url + '?' + querystring.stringify(data);
    })
```

https://translate.google.com/translate_a/single?client=gtx&dj=1&sl=en&tl=zh&hl=en&dt=at&dt=bd&dt=ex&dt=ld&dt=md&dt=qca&dt=rw&dt=rm&dt=ss&dt=t&ie=UTF-8&oe=UTF-8&otf=1&ssel=0&tsel=0&kc=7&tk=685532.807248&q=shoe