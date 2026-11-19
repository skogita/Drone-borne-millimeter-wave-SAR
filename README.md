# Drone-borne millimeter-wave SAR processing system (dronesar) and apps — companion source for the book

Design documents and code for the drone-borne millimeter-wave SAR processing system built in ***Toward a Million Lines XXVII — Building a Drone-Borne Millimeter-Wave SAR Processing App Yourself, from Simulated Raw Data*** (Japanese title 『LLM で 100 万行のソフトウェア開発 XXVII — 模擬の生データから、ドローン搭載ミリ波 SAR の処理アプリを自分で作る』; the book is in Japanese).

The book is a design-and-simulation study of a chip-class 77 to 81 GHz FMCW MIMO radar (2 transmit and 4 receive channels, 8 virtual channels) flown on a drone, with the synthetic aperture along the flight direction. There is no real vehicle and no real flight data: everything runs on simulated raw data with a truth table.

The processing system `dronesar` (Python) simulates the raw beat signal, reads it, preprocesses it, compresses it in range, compensates the motion, focuses the image (autofocus, back-projection), measures the height from the elevation channels by interferometry, averages looks, detects targets, geocodes the result to a map and compares it with the truth table. Two **separate** Windows apps (Flutter) sit on top of it: a **processing app** and a **simulator app**.

## Download

**Ready-to-run apps and the source are on the [Releases](../../releases) page**, not in this repository. The release has three separate ZIPs:

| File | Contents |
|:---|:---|
| `dronesar_exe.zip` | The two Windows apps, ready built (**Japanese screens**), in separate folders (`processor\` and `simulator\`), with a copy of the processing system (`tools_for_run\`) |
| `dronesar_exe_en.zip` | The same two apps (**English screens**) |
| `dronesar.zip` | Design documents (`docs/`, Japanese, L1-L4, the source; `docs_en/`, the complete set for the English edition: L1-L3 translated into English, L4 the Japanese originals as is) in separate folders, the code (`src/dronesar/`, `app/`, and `edition_en/`, a copy of the code and apps with English as the default language), empty databases and the license files |

The apps need Python 3.11 on your PC (see the README inside the ZIPs; run `pip install .`). There is **no APK** (the apps are Windows desktop apps). The apps are **not code-signed**, so Windows may warn you. Data, tests and processing results are not included; the simulator can make raw data of the same form as the data used in the book, with a truth table.

You are free to change the design documents and the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, `docs_en/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code.** When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (numpy, scipy, h5py, numba installed by `pip install .`; the Flutter engine inside the EXEs) remain under their own original licenses.
- The rights to the elevation data used for the example scene in the book (the Geospatial Information Authority of Japan, Fundamental Geospatial Data, DEM 5 m mesh) stay with the provider. The data are not in this repository. The raw data the simulator writes are simulated values.
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・`docs_en/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です。**コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- 第三者の部品（`pip install .` で入る numpy・scipy・h5py・numba、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 本の例の場面に使った標高データ（国土地理院 基盤地図情報 数値標高モデル 5 m メッシュ）の権利は、提供元に残ります。データはこのリポジトリに含みません。シミュレータが書く生データは、模擬の値です。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。
