---
title: "액셀러레이터 키 형식 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type 속성"
  - "VIRTKEY"
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 액셀러레이터 키 형식 속성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

액셀러레이터 키 **형식** 속성은 액셀러레이터 키 ID와 연결된 바로 가기 키 조합이 가상 키 조합인지 ASCII\/ANSI 키 값인지를 결정합니다.  
  
-   **형식** 속성이 **ASCII**이면 [한정자](../windows/accelerator-modifier-property.md)가 없음이나 Alt 키만 될 수도 있고, 키 앞에 ^ 기호를 넣어 Ctrl 키를 지정하면 Ctrl 키를 사용하는 액셀러레이터 키를 가질 수도 있습니다.  
  
-   **형식** 속성이 **VIRTKEY**이면 한정자와 키 값으로 구성된 모든 조합을 사용할 수 있습니다.  
  
    > [!NOTE]
    >  액셀러레이터 키 테이블에 값을 입력하고 입력한 값이 ASCII\/ANSI로 처리되도록 하려면, 테이블에서 항목에 대한 형식을 누르고 드롭다운 목록에서 ASCII를 선택하십시오.  **다음 입력된 키** 명령\(**편집** 메뉴\)을 사용하여 키를 지정하는 경우에는 키 코드를 입력하기 *전에* **형식** 속성을 VIRTKEY에서 ASCII로 변경해야 합니다.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)