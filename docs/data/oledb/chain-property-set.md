---
title: "CHAIN_PROPERTY_SET | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CHAIN_PROPERTY_SET"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHAIN_PROPERTY_SET 매크로"
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CHAIN_PROPERTY_SET
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 매크로는 속성 그룹을 함께 연결합니다.  
  
## 구문  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
```  
  
#### 매개 변수  
 *ChainClass*  
 \[in\] 체인 속성에 대한 클래스의 이름입니다.  지도 \(예: 세션, 명령 또는 데이터 원본 개체 클래스\)를 포함하여 ATL 프로젝트 마법사에 의해 이미 생성된 클래스입니다.  
  
## 설명  
 그런 다음 자신의 클래스에 다른 클래스에서 설정한 속성을 연결하고, 클래스에서 직접 속성에 액세스할 수 있습니다.  
  
> [!CAUTION]
>  이 매크로를 자주 사용합니다.  부적절한 사용 소비자 OLE DB 규칙 테스트에 실패할 수 있습니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)