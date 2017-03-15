---
title: "액셀러레이터 키 한정자 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Modifier 속성"
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 액셀러레이터 키 한정자 속성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 액셀러레이터 키 테이블의 한정자 속성에 사용할 수 있는 항목에 대한 설명입니다.  
  
|값|설명|  
|-------|--------|  
|**없음**|사용자가 키 값만 누릅니다.  이것은 ^A부터 ^Z\(Ctrl–A부터 Ctrl\-Z\)으로 해석되는 ASCII\/ANSI 값 001–026에 가장 효과적으로 사용되는 값입니다.|  
|**Alt**|키 값을 누르기 전에 Alt 키를 먼저 눌러야 합니다.|  
|**Ctrl**|키 값을 누르기 전에 Ctrl 키를 먼저 눌러야 합니다.  ASCII 형식과 함께 사용할 수 없습니다.|  
|**시프트 연산자**|키 값을 누르기 전에 Shift 키를 먼저 눌러야 합니다.|  
|**Ctrl\+Alt**|키 값을 누르기 전에 Ctrl\+Alt를 먼저 눌러야 합니다.  ASCII 형식과 함께 사용할 수 없습니다.|  
|**Ctrl\+Shift**|키 값을 누르기 전에 Ctrl\+Shift를 먼저 눌러야 합니다.  ASCII 형식과 함께 사용할 수 없습니다.|  
|**Alt\+Shift**|키 값을 누르기 전에 Alt\+Shift를 먼저 눌러야 합니다.  ASCII 형식과 함께 사용할 수 없습니다.|  
|**Ctrl\+Alt\+Shift**|키 값을 누르기 전에 Ctrl\+Alt\+Shift를 먼저 눌러야 합니다.  ASCII 형식과 함께 사용할 수 없습니다.|  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)