### **DICOM RDSR（Radiation Dose Structured Report）とは？**  
**DICOM RDSR（Radiation Dose Structured Report）** は、放射線被ばく情報をDICOMの**構造化レポート（Structured Report, SR）**として記録するための規格です。  
通常のDICOM SRの一種ですが、特に**CTやX線撮影などでの放射線量を記録・管理するために特化**しています。  

---

## **DICOM RDSRの目的**
1. **患者の被ばく線量の記録・管理**
   - CT、X線、血管造影（Angiography）、マンモグラフィなどの放射線検査で患者が受けた**被ばく線量を標準フォーマットで保存**  
   - 医療機関間で統一的な管理が可能  

2. **線量管理システム（Dose Management System）との連携**
   - 医療機関では、放射線被ばくをモニタリングするための「**線量管理システム**」を導入していることが多い  
   - DICOM RDSRを活用することで、線量データを自動的に収集・解析可能  

3. **放射線防護（Radiation Protection）と規制対応**
   - 各国の放射線被ばくガイドライン（例: 欧州のEURATOM、日本のJSRTガイドライン）への適合  
   - 被ばく線量が過剰にならないように管理し、**ALARA（As Low As Reasonably Achievable）**の原則に従う  

---

## **DICOM RDSRの記録内容**
DICOM RDSRには、以下のような情報がツリー構造で保存されます。  

```
├─ 患者情報（Patient Information）
│   ├─ 氏名：田中太郎
│   ├─ 生年月日：1970-05-10
│   ├─ 患者ID：123456
├─ 検査情報（Study Information）
│   ├─ 検査日：2025-03-10
│   ├─ モダリティ：CT
│   ├─ 検査機器：GE Revolution CT
├─ 被ばく情報（Radiation Dose Information）
│   ├─ 総線量（Total Dose）：850 mGy·cm
│   ├─ 各シリーズの線量情報
│   │   ├─ Series 1（胸部CT）
│   │   │   ├─ CTDIvol（mGy）：12.5
│   │   │   ├─ DLP（mGy·cm）：250
│   │   ├─ Series 2（腹部CT）
│   │   │   ├─ CTDIvol（mGy）：15.0
│   │   │   ├─ DLP（mGy·cm）：600
│   ├─ 撮影条件（Exposure Parameters）
│   │   ├─ 管電圧（kVp）：120
│   │   ├─ 管電流（mAs）：300
│   ├─ 線量参照レベル（Diagnostic Reference Levels, DRL）との比較
│   │   ├─ 施設基準：OK（基準内）
│   │   ├─ 国際基準：OK（基準内）
```

---

## **DICOM RDSRの活用例**
### **① 放射線被ばく線量の管理**
- **患者ごとに被ばく線量を記録**し、不要な被ばくを防ぐ  
- 被ばく線量が規定値を超えた場合にアラートを発する  

### **② 線量最適化**
- 検査ごとの線量データを蓄積し、適切な撮影条件を設定  
- AI解析を用いた**線量最適化（Dose Optimization）**にも活用  

### **③ 規制遵守と監査**
- 規制当局への報告（例：米国の**Joint Commission**、欧州の**EURATOM**など）  
- **病院の放射線防護監査**のためのデータ管理  

---

## **DICOM RDSRのメリット**
✅ **標準フォーマットでの記録**（異なるメーカーの装置でも統一的に管理可能）  
✅ **被ばく情報の自動収集・分析が可能**（手作業での記録ミスを防ぐ）  
✅ **患者ごとの線量最適化に貢献**（ALARA原則の実践）  

---

## **DICOM RDSRの閲覧・管理**
- **DICOMビューア**（OsiriX、RadiAntなど）  
- **線量管理システム（Dose Management System）**  
  - GE DoseWatch  
  - Bayer Radimetrics  
  - PACSの線量管理機能  

---

### **まとめ**
- **DICOM RDSR（Radiation Dose Structured Report）は、放射線検査の被ばく線量を記録するDICOMの標準フォーマット**  
- **CT、X線、血管造影などの検査で受けた線量を詳細に保存**  
- **線量管理システムと連携し、患者の被ばく線量を最適化・監視**  
- **規制対応（ALARA原則、EURATOM、JSRTガイドライン）にも活用**  

DICOM RDSRは、**医療被ばくの適正管理を支える重要な技術**です。