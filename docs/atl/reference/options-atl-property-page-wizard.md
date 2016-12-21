---
title: "옵션, ATL 속성 페이지 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.ppg.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 속성 페이지 마법사, 옵션"
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 옵션, ATL 속성 페이지 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마법사의 이 페이지에서는 만들려는 속성 페이지의 스레딩 모델과 집계 수준을 정의합니다.  
  
 **스레딩 모델**  
 속성 페이지에서 사용하는 스레딩 모델을 지정합니다.  
  
 자세한 내용은 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md)을 참조하십시오.  
  
|옵션|설명|  
|--------|--------|  
|`Single`|속성 페이지는 기본 COM 스레드에서만 실행됩니다.|  
|**아파트**|모든 단일 스레드 아파트에서 속성 페이지를 만들 수 있습니다.  기본값입니다.|  
  
 **집계**  
 만들려는 속성 페이지에 집계 기능을 추가합니다.  자세한 내용은 [집합체](../../atl/aggregation.md)를 참조하십시오.  
  
|옵션|설명|  
|--------|--------|  
|**예**|집계할 수 있는 속성 페이지를 만듭니다.|  
|**아니요**|집계할 수 없는 속성 페이지를 만듭니다.|  
|**전용**|집계를 통해서만 인스턴스로 생성될 수 있는 속성 페이지를 만듭니다.|  
  
## 참고 항목  
 [ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)   
 [문자열, ATL 속성 페이지 마법사](../../atl/reference/strings-atl-property-page-wizard.md)