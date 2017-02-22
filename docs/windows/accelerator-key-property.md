---
title: "액셀러레이터 키 속성 | Microsoft Docs"
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
  - "키 속성"
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 액셀러레이터 키 속성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 액셀러레이터 키 테이블의 키 속성에 사용할 수 있는 항목에 대한 설명입니다.  
  
-   0과 255 사이의 10진수 형식 정수.  다음 기준에 따라 값을 ASCII로 처리할지 ANSI로 처리할지를 결정합니다.  
  
    -   한 자리 수는 항상 ASCII나 ANSI 값이 아닌 해당 키로 해석됩니다.  
  
    -   1부터 26까지의 값 앞에 0이 있으면 ^A부터 ^Z로 해석되며, 이것은 Ctrl 키와 함께 영문자를 누른 경우 해당 문자의 ASCII 값을 나타냅니다.  
  
    -   27부터 32까지의 값은 항상 세 자리 10진수 값 027부터 032로 해석됩니다.  
  
    -   033부터 255까지의 값은 앞에 0이 있든지 없든지에 관계 없이 ANSI 값으로 해석됩니다.  
  
-   단일 키보드 문자.  대문자 A–Z 또는 숫자 0–9는 ASCII 값이나 가상 키 값이 될 수 있지만, 이 외의 다른 문자는 ASCII 값만 될 수 있습니다.  
  
-   앞에 캐럿\(^\)이 있는 대문자 A–Z 범위의 단일 키보드 문자\(예: ^C\).  Ctrl 키와 함께 이 범위의 대문자를 누르면 해당 키의 ASCII 값이 입력됩니다.  
  
    > [!NOTE]
    >  ASCII 값을 입력할 때는 한정자 속성 옵션이 제한됩니다.  따라서 Alt 키만 제어 키로 사용할 수 있습니다.  
  
-   올바른 가상 키 식별자.  액셀러레이터 키 테이블의 드롭다운 키 상자에는 표준 가상 키 식별자 목록이 있습니다.  
  
    > [!TIP]
    >  액셀러레이터 키를 다른 방법으로 정의하려면 액셀러레이터 키 테이블에서 하나 또는 여러 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **다음 입력된 키**를 선택한 다음, 키보드에서 키나 키 조합을 누르면 됩니다.  **다음 입력된 키** 명령은 **편집** 메뉴에서도 사용할 수 있습니다.  
  
## 요구 사항  
 Win32  
  
## 참고 항목  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Editing in an Accelerator Table](../windows/editing-in-an-accelerator-table.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)