# assdumper

Parse ARIB caption data from MPEG2-TS file.

## How to use

Compiler the source code (require g++):

    $ make

Dump the caption data in ASS format:

    $ ./assdumper video.m2ts

Dump the caption data in TSV format:

    $ ./tsvdumper video.m2ts

## Output Example

### assdumper

assdumper outputs in ASS format. For details, please read [this article](https://en.wikipedia.org/wiki/SubStation_Alpha#Advanced_SubStation_Alpha).

```
$ assdumper video.m2ts
...
[Events]
Dialogue: 0,00:00:04.11,00:00:07.45,Default,,,,,, 生字幕放送です。一部、字幕で 表現しきれない場合があります。
Dialogue: 0,00:00:07.45,00:00:20.88,Default,,,,,,
Dialogue: 0,00:00:20.88,00:00:24.66,Default,,,,,, こんにちは。正午のニュースです。
Dialogue: 0,00:00:24.66,00:00:29.85,Default,,,,,,
Dialogue: 0,00:00:29.85,00:00:33.77,Default,,,,,, 北海道の知床半島沖で観光船が
...
```

### tsvdumper

tsvdumper outputs each caption in the format of `(start_in_msec, end_in_msec, caption)`.

```
$ tsvdumper video.m2ts
4578    7914     生字幕放送です。一部、字幕で 表現しきれない場合があります。
7914    21344
21344   25132    こんにちは。正午のニュースです。
25132   30320
30320   34241    北海道の知床半島沖で観光船が
...
```
