---
title: "CDaoIndexFieldInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoIndexFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoIndexFieldInfo 구조체"
  - "DAO(Data Access Objects), 인덱스 필드 컬렉션"
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDaoIndexFieldInfo 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoIndexFieldInfo` 구조체는 데이터 액세스 개체 \(DAO\)에 정의 된 인덱스 필드 개체에 대한 정보가 들어 있습니다.  
  
## 구문  
  
```  
  
      struct CDaoIndexFieldInfo  
{  
   CString m_strName;          // Primary  
   BOOL m_bDescending;         // Primary  
};  
```  
  
#### 매개 변수  
 `m_strName`  
 고유 인덱스 필드 개체의 이름을 지정 합니다.  자세한 내용은 DAO 도움말의 "속성 이름" 항목을 참조 하십시오.  
  
 *m\_bDescending*  
 인덱스 개체에 정의 된 인덱스 순서를 나타냅니다.  명령이 내림차순인 경우 **TRUE** 입니다.  
  
## 설명  
 인덱스 개체가 테이블 정의 \(또는 테이블을 기반으로 레코드 집합\)에서 인덱싱된 필드를 나타내는 필드의 번호를 가질 수 있습니다.  [CDaoTableDef](../Topic/CDaoTableDef::GetIndexInfo.md) 또는 [CDaoRecordset](../Topic/CDaoRecordset::GetIndexInfo.md) 클래스의 `GetIndexInfo` 멤버 함수를 호출하여 얻어지는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 개체의 `m_pFieldInfos` 멤버에서 어떻게 정보를 반환 할 것인지를 나타내는 것 이상의 참조입니다.  
  
 인덱스 및 인덱스 필드 개체는 MFC 클래스에 의해 표시 되지 않습니다.  대신, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) or [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 클래스의 MFC 개체내에 DAO 개체는 인덱스 컬렉션을 호출하여 인덱스 개체의 컬렉션을 포함합니다.  각 인덱스 개체 필드 개체의 컬렉션을 포함합니다.  이러한 클래스는 멤버 함수를 인덱스 정보의 개별 아이템에 액세스하도록 제공합니다 또는 포함하는 개체의 `GetIndexInfo` 멤버 함수를 호출하여 `CDaoIndexInfo` 개체를 사용하여 모든 아이템에 한번에 액세스 할 수 있습니다.  `CDaoIndexInfo` 개체는 그다음 `m_pFieldInfos` 데이터 멤버를 가지고, `CDaoIndexFieldInfo` 개체의 배열을 가르킵니다.  
  
 관심 있는 인덱스 개체가 저장된 인덱스 콜렉션에 포함된 tabledef 또는 레코드 집합 개체의 `GetIndexInfo` 멤버 함수를 호출하십시오.  그 다음 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 개체의 `m_pFieldInfos` 멤버에 액세스 합니다.  `m_pFieldInfos` 배열의 길이는 `m_nFields` 에 저장됩니다.  `CDaoIndexFieldInfo` 는 디버그 빌드에서 `Dump` 멤버 함수를 정의합니다.  `Dump` 를 사용하여 `CDaoIndexFieldInfo` 개체의 컨텐츠를 버릴 수 있습니다.  
  
## 요구 사항  
 **Header:** afxdao.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)   
 [CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)