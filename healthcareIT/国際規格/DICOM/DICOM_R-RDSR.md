### **DICOM R-RDSR（Radiopharmaceutical Radiation Dose Structured Report）とは？**  

**DICOM R-RDSR（Radiopharmaceutical Radiation Dose Structured Report）** は、**核医学（Nuclear Medicine, NM）やPET（Positron Emission Tomography）検査における放射性医薬品の投与線量を記録するDICOM SRの一種** です。  

通常の **DICOM RDSR**（X線やCTの被ばく線量記録）と異なり、**放射性医薬品（ラジオアイソトープ, RI）の投与情報と、それによる患者の内部被ばく線量** を記録します。  

---

## **DICOM R-RDSRの目的**
1. **核医学検査で使用する放射性医薬品の線量管理**  
   - 患者ごとに投与した放射性医薬品の種類、量（MBq）、生物学的半減期などを記録  

2. **内部被ばく線量の記録・管理**  
   - X線やCTのような外部被ばく（External Dose）ではなく、体内で崩壊する放射性物質による**内部被ばく（Internal Dose）** を記録  

3. **線量最適化と規制対応**  
   - **ALARA（As Low As Reasonably Achievable）** 原則に基づいた放射線管理  
   - 各国の規制（例：ICRP、NRC、EURATOM）への対応  

---

## **DICOM R-RDSRの記録内容**
DICOM R-RDSRは、**放射性医薬品の投与データや内部被ばく線量をツリー構造で記録** します。

```
├─ 患者情報（Patient Information）
│   ├─ 氏名：田中太郎
│   ├─ 生年月日：1970-05-10
│   ├─ 患者ID：123456
├─ 検査情報（Study Information）
│   ├─ 検査日：2025-03-10
│   ├─ モダリティ：PET-CT
│   ├─ 使用機器：Siemens Biograph mCT
├─ 放射性医薬品情報（Radiopharmaceutical Information）
│   ├─ 投与薬剤：Fluorodeoxyglucose（FDG）
│   ├─ 放射性核種（Radionuclide）：F-18（フッ素-18）
│   ├─ 投与量（Administered Activity）：185 MBq
│   ├─ 投与時間（Administration Time）：10:15 AM
│   ├─ 生物学的半減期（Biological Half-life）：110分
│   ├─ 物理学的半減期（Physical Half-life）：109.8分
├─ 内部被ばく線量（Internal Dose）
│   ├─ 臓器別線量（Organ Dose）
│   │   ├─ 脳：12 mSv
│   │   ├─ 心臓：8 mSv
│   │   ├─ 肝臓：15 mSv
│   ├─ 有効線量（Effective Dose）：7.5 mSv
│   ├─ 参照基準（Diagnostic Reference Levels, DRL）との比較
│   │   ├─ 施設基準：OK（基準内）
│   │   ├─ 国際基準：OK（基準内）
```

---

## **DICOM R-RDSRの活用例**
### **① 核医学検査の線量管理**
- **PET-CT, SPECT, シンチグラフィ検査で投与されたRIの管理**  
- **投与線量、臓器別線量、半減期などを自動記録**  

### **② 被ばく線量の最適化**
- **患者の年齢・体重に応じた放射性医薬品の適正投与**  
- **放射線治療計画（Radionuclide Therapy）における線量調整**  

### **③ 規制対応と監査**
- **国際基準（ICRP, EURATOM, NRC）の遵守**  
- **病院や放射線防護機関での監査**  

---

## **DICOM R-RDSRのメリット**
✅ **標準フォーマットでの記録**（異なるメーカーの装置でも統一的に管理可能）  
✅ **投与データの自動収集・分析が可能**（手作業の記録ミスを防ぐ）  
✅ **患者ごとの線量最適化に貢献**（ALARA原則の実践）  

---

## **DICOM R-RDSRの閲覧・管理**
- **DICOMビューア（OsiriX、RadiAntなど）**  
- **線量管理システム（Dose Management System）**  
  - GE DoseWatch  
  - Bayer Radimetrics  
  - Hermes Medical Solutions  

---

### **まとめ**
- **DICOM R-RDSR（Radiopharmaceutical Radiation Dose Structured Report）は、核医学（PET, SPECT）で使用する放射性医薬品の投与線量を記録するDICOM SRフォーマット**  
- **投与量（MBq）、内部被ばく線量（mSv）、臓器別線量を詳細に保存**  
- **線量管理システムと連携し、患者ごとの被ばく線量を最適化・監視**  
- **規制対応（ALARA原則、ICRP、EURATOM、NRC）にも活用**  

DICOM R-RDSRは、**核医学の被ばく線量管理を標準化し、安全で適切な診断・治療を支える重要な技術** です。