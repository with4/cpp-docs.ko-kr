---
title: "Visual C++ 문서 태그의 구분 기호 | Microsoft Docs"
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
  - "XML 문서, 구분 기호"
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ 문서 태그의 구분 기호
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문서 태그를 사용 하는 문서 주석이 시작 되 고 끝나는 위치를 컴파일러에 알리는 구분 기호를 해야 합니다.  
  
 XML 문서 태그에는 다음과 같은 구분 기호를 사용할 수 있습니다.  
  
 `///`  
 이 문서 예제에 표시 되 고 Visual C\+\+ 프로젝트 템플릿에서 사용 하는 폼입니다.  
  
 `/** */`  
 이러한 여러 줄 구분 기호입니다.  
  
 사용할 때는 몇 가지 서식 규칙이 가지는 `/** */` 구분 기호:  
  
-   포함 하는 줄의 `/**` 구분 기호가 있는 줄의 나머지 부분이 공백 줄이 주석으로 처리 되지 않습니다.  첫 번째 문자가 공백인 경우 공백 문자가 무시 되 고 줄의 나머지 부분이 처리 됩니다.  그렇지 않으면 `/**` 구분 기호 뒤에 나오는 전체 텍스트가 주석의 일부로 처리됩니다.  
  
-   포함 하는 줄의 `*/` 공백만 있으면 구분의 `*/` 구분 기호가 해당 줄이 무시 됩니다.  그렇지 않으면 `*/` 구분 기호 앞의 텍스트가 다음 목록에서 설명하는 패턴 일치 규칙에 따라 주석의 일부로 처리됩니다.  
  
-   줄 뒤에 시작 하는 것은 `/**` 구분 컴파일러 찾고 선택적 공백 및 별표 구성 하는 각 줄의 시작 부분에서 공통 패턴이 \(`*`\), 추가 선택적 공백의 뒤.  컴파일러가 각 줄의 시작 부분에 일반적인 문자 집합을 찾으면 해당 패턴을 뒤의 모든 줄을 무시 합니다의 `/**` 구분 기호를 설정 하 고 포함 된 줄을 포함 하 여은 `*/` 구분 합니다.  
  
 예제는 다음과 같습니다.  
  
-   다음 주석에서는 `<summary>`로 시작하는 줄만 처리됩니다.  다음 두 가지 태그 형식 같은 주석을 만듭니다.  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   컴파일러가 패턴을 적용 "\*" 두 번째 및 세 번째 줄의 시작 부분에 무시 합니다.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   두 번째 줄에 별표가 없으므로 컴파일러가 패턴을이 주석에서 찾습니다.  모든 텍스트에서 두 번째 및 세 번째 줄, 따라서 앞의 `*/`를 주석의 일부로 처리 됩니다.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   컴파일러는 두 가지 이유로이 주석에 패턴을 찾지 못합니다.  첫째, 별표 앞의 공백 수가 서로 일치 시작 선 없음입니다.  둘째, 다섯 번째 줄이 탭으로 시작하는데, 탭은 공백과 일치하지 않습니다.  따라서 모든 텍스트에서 두 번째 줄부터의 `*/` 주석의 일부로 처리 됩니다.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)