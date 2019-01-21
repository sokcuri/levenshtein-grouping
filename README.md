## Levenshtein grouping
편집 거리 알고리즘 (Levenshtein 알고리즘)을 이용해서 파일들을 그룹핑하는 예제입니다

데이터는 냐토렌트 (https://nyaa.si)에서, 그룹핑을 위한 필터 함수는 스택오버플로우의 [Group similar strings from an array in Node.js](https://stackoverflow.com/questions/42213194/group-similar-strings-from-an-array-in-node-js) 토픽에서 가져왔습니다.

### How to run
```
npm install
npm start
```

### Input
```
...
    "[Ohys-Raws] Grimms Notes The Animation - 01 (TBS 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Go-Toubun no Hanayome - 01 (TBS 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Yakusoku no Neverland - 01 (CX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Bang Dream! 2nd Season - 02 (AT-X 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Girly Air Force - 01 (AT-X 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Karakuri Circus - 13 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Kirakira Happy Hirake! Cocotama - 18 (TX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Aikatsu Friends! - 39 (TX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Revisions - 01 (CX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Virtual-san wa Miteiru - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Kemurikusa (2019) - 01 (BSFUJI 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Meiji Tokyo Renka - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Doukyonin wa Hiza, Tokidoki, Atama no Ue. - 01 (AT-X 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Tate no Yuusha no Nariagari - 01 (AT-X 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Kakegurui XX - 01 (MBS 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] 3D Kanojo Real Girl (2019) - 01 (NTV 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Kaze ga Tsuyoku Fuite Iru - 12 (NTV 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Ame-iro Cocoa Side G - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Rinshi!! Ekoda-chan - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Circlet Princess - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Kemono Friends 2 - TVSP (TX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Watashi ni Tenshi ga Maiorita! - 01 (AT-X 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Black Clover - 65 (TX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Pastel Memories - 01 (BSFUJI 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Tensei Shitara Slime Datta Ken - 14 (BS11 1920x1080 x264 AAC).mp4",
    "[Ohys-Raws] Tensei Shitara Slime Datta Ken - 14 (BS11 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Mob Psycho 100 II - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Dororo (2019) - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Papa Datte, Shitai - 01 (MX 1280x720 x264 AAC).mp4",
    "[Ohys-Raws] Ueno-san wa Bukiyou - 01 (BS11 1280x720 x264 AAC).mp4",
...
```


### Result
```
...
  [ '[Ohys-Raws] Tensei Shitara Slime Datta Ken - 14 (BS11 1920x1080 x264 AAC).mp4',
    '[Ohys-Raws] Tensei Shitara Slime Datta Ken - 15 (BS11 1920x1080 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Pastel Memories - 01 (BSFUJI 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Pastel Memories - 02 (BSFUJI 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Watashi ni Tenshi ga Maiorita! - 01 (AT-X 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Watashi ni Tenshi ga Maiorita! - 02 (AT-X 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Kemono Friends 2 - TVSP (TX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Kemono Friends 2 - 01 (TX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Circlet Princess - 01 (MX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Circlet Princess - 02 (MX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Rinshi!! Ekoda-chan - 01 (MX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Rinshi!! Ekoda-chan - 02 (MX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Ame-iro Cocoa Side G - 01 (MX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Ame-iro Cocoa Side G - 02 (MX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Kaze ga Tsuyoku Fuite Iru - 12 (NTV 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Kaze ga Tsuyoku Fuite Iru - 13 (NTV 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] 3D Kanojo Real Girl (2019) - 01 (NTV 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] 3D Kanojo Real Girl (2019) - 02 (NTV 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Kakegurui XX - 01 (MBS 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Kakegurui XX - 02 (MBS 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Tate no Yuusha no Nariagari - 01 (AT-X 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Tate no Yuusha no Nariagari - 02 (AT-X 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Doukyonin wa Hiza, Tokidoki, Atama no Ue. - 01 (AT-X 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Doukyonin wa Hiza, Tokidoki, Atama no Ue. - 02 (AT-X 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Meiji Tokyo Renka - 01 (MX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Meiji Tokyo Renka - 02 (MX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Kemurikusa (2019) - 01 (BSFUJI 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Virtual-san wa Miteiru - 01 (MX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Virtual-san wa Miteiru - 02 (MX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Revisions - 01 (CX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Revisions - 02 (CX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Girly Air Force - 01 (AT-X 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Girly Air Force - 02 (AT-X 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Yakusoku no Neverland - 01 (CX 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Yakusoku no Neverland - 02 (CX 1280x720 x264 AAC).mp4' ],
  [ '[Ohys-Raws] Go-Toubun no Hanayome - 01 (TBS 1280x720 x264 AAC).mp4',
    '[Ohys-Raws] Go-Toubun no Hanayome - 02 (TBS 1280x720 x264 AAC).mp4' ],
...
```

### levenshteinFilter
* [Group similar strings from an array in Node.js](https://stackoverflow.com/questions/42213194/group-similar-strings-from-an-array-in-node-js)
