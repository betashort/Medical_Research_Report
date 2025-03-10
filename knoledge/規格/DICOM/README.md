# DICOMとは

DICOM（Digital Imaging and Communications in Medicine）は、医療用画像の保存・送信・共有を目的とした国際規格です。  
放射線画像（X線、CT、MRIなど）をはじめとする医療画像のデータフォーマットや通信プロトコルを定めています。  

## **DICOMの主な特徴**

1. **画像の標準フォーマット**  
   - CT、MRI、超音波、X線などの医用画像を統一された形式で保存
   - 画像データに患者情報や撮影条件などのメタデータを埋め込む

2. **ネットワーク通信プロトコル**  
   - 病院内のPACS（医療画像管理システム）や医療機器間で画像をやり取りできる
   - DICOMノード（DICOM対応機器）同士がデータ送受信できる

3. **階層構造（DICOMデータの管理単位）**  
   - **Patient（患者）**：患者ごとの情報（氏名、ID、生年月日など）
   - **Study（検査）**：検査単位（CT検査1回分など）
   - **Series（シリーズ）**：撮影条件ごとの画像のまとまり
   - **Image（画像）**：1枚ごとの医用画像データ

4. **ファイルの拡張子**  
   - 一般的に `.dcm` （DICOMファイル）として保存される

5. **DICOMビューア**  
   - DICOM画像は一般的な画像ビューワ（JPEG, PNG対応）では開けない
   - **OsiriX、RadiAnt DICOM Viewer、Horos** などの専用ソフトが必要  

## **DICOMの活用例**
- 病院間での医用画像データの共有  
- 放射線科、循環器科、整形外科などでの診断  
- AIを用いた医用画像解析  
- 遠隔医療（テレラジオロジー）  

DICOMは、医療現場のデジタル化を支える重要な技術です。

## DICOMの種類

DICOMには、用途や機能に応じたさまざまな種類（DICOMサービスクラスやオブジェクト）があります。以下に代表的な種類を紹介します。

---

### **(1) 画像データ（Image Objects）**

DICOMはさまざまな医療画像をサポートしています。

- **CR（Computed Radiography）**：デジタルX線画像
- **CT（Computed Tomography）**：CTスキャン画像
- **MR（Magnetic Resonance）**：MRI画像
- **US（Ultrasound）**：超音波画像
- **XA（X-ray Angiography）**：X線血管造影画像
- **NM（Nuclear Medicine）**：核医学画像
- **MG（Mammography）**：マンモグラフィ画像
- **SC（Secondary Capture）**：JPEGやPNGをDICOMに変換した画像

### **(2) 非画像データ**

DICOMは画像だけでなく、関連する情報も扱えます。

- [**SR（Structured Report）**：検査結果レポート](./DICOM_SR.md)
  - [DICOM RDSR（Radiation Dose Structured Report）](./DICOM_RDSR.md)
  - [DICOM R-RDSR（Radiopharmaceutical Radiation Dose Structured Report）](./DICOM_R-RDSR.md)
- **Waveform（波形データ）**：心電図（ECG）、脳波（EEG）  
- **RT（Radiotherapy）**：放射線治療データ（計画、線量分布など）  
- **Presentation State（PS）**：表示設定（ウィンドウ幅・レベル、アノテーションなど）  

---

### **2. DICOMの通信プロトコル（DICOMサービスクラス）**

DICOMは、医療機器やPACS（医用画像管理システム）との通信にも対応しています。

#### **(1) 画像の送受信**

- [**DICOM Storage**（画像保存）：画像を送受信する](./DICOM_Strage.md)  
- [**DICOM Query/Retrieve**（検索・取得）：PACSから画像を検索・取得する](./DICOM_QR.md)

#### **(2) ワークリスト（作業リスト）**

- **DICOM Modality Worklist（MWL）**：検査予約情報を取得し、装置に反映する  
- **DICOM Modality Performed Procedure Step（MPPS）**：撮影完了情報を送信する  

#### **(3) プリントとストレージ**

- **DICOM Print**：DICOM対応プリンターで画像を印刷  
- **DICOM Storage Commitment**：画像が正常に保存されたことを保証する  

#### **(4) 画像転送（遠隔医療）**

- **DICOM Web（WADO, QIDO, STOW）**：Web経由でDICOMデータを送受信  
  - WADO（Web Access to DICOM Objects）：WebブラウザでDICOM画像を見る  
  - QIDO（Query based on ID for DICOM Objects）：DICOMデータを検索  
  - STOW（Store Over the Web）：DICOM画像をWeb経由で保存  

---

### **3. DICOMの圧縮方式**

DICOMファイルは、圧縮方法によっても種類が分かれます。

- **無圧縮（Raw）**：元の画質を維持  
- **可逆圧縮（Lossless）**：JPEG-LS, JPEG 2000 Lossless（画質を劣化させずに圧縮）  
- **非可逆圧縮（Lossy）**：JPEG, JPEG 2000 Lossy（画質を若干落としながら圧縮）  

---

DICOMは「画像フォーマット」としての側面だけでなく、「ネットワーク通信プロトコル」としての役割も持っています。医療現場では、これらの種類を適切に使い分けながら、画像管理や診断を行っています。