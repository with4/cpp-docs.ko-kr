---
title: "Visual c + + 문서 태그의 구분 기호 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 134605f86ef8019d34f5246fd75abbbf94d40fbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Visual C++ 문서 태그의 구분 기호
문서 태그의을 사용 하려면 문서 주석의 시작 및 종료를 컴파일러에 알리는 구분 기호입니다.  
  
 XML 문서 태그에 다음과 같은 종류의 구분 기호를 사용할 수 있습니다.  
  
 `///`  
 문서 예제에 표시 되 고 Visual c + + 프로젝트 템플릿을 사용 하는 폼입니다.  
  
 `/** */`  
 이들은 여러 줄 구분 기호입니다.  
  
 몇 가지 서식을 사용 하는 경우 규칙을 가지는 `/** */` 구분 기호:  
  
-   포함 하는 줄에 대 한는 `/**` 구분 기호, 줄의 나머지 부분이 공백이 해당 줄이 주석 처리 되지 않습니다. 첫 번째 문자가 공백 이면 공백 문자가 무시 되 고 해당 줄의 나머지 부분이 처리 됩니다. 그러지 않으면 `/**` 구분 기호 다음 줄의 전체 텍스트가 주석의 일부로 처리됩니다.  
  
-   포함 하는 줄에 대 한는 `*/` 최대 공백인 경우 구분 기호는 `*/` 구분 기호를 해당 줄은 무시 됩니다. 그러지 않으면 줄의 텍스트가 `*/` 구분 기호까지 주석의 일부로 처리되며, 다음 글머리 기호에서 설명하는 패턴 일치 규칙을 따릅니다.  
  
-   줄으로 시작 하는 뒤에 대 한는 `/**` 와 별표 구성 된 각 줄의 시작 부분에는 일반적인 패턴에 대 한 구분 기호, 컴파일러 찾습니다 (`*`) 선택적 공백을 이어집니다. 컴파일러가 각 줄의 시작 부분에는 공통 집합이 문자를 발견할 경우 모든 줄 뒤에 대 한 패턴을 무시 합니다는 `/**` 및까지 가능 포함 하는 줄 구분 기호는 `*/` 구분 기호입니다.  
  
 몇 가지 예:  
  
-   다음 주석에서 유일하게 처리되는 부분은 `<summary>`로 시작하는 줄입니다. 다음 두 가지 형식의 태그는 같은 주석을 생성 합니다.  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   컴파일러의 패턴을 적용 "*"를 두 번째 및 세 번째 줄의 시작 부분에서 무시 합니다.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   컴파일러가 두 번째 줄에 별표가 있기 때문에이 메모에 있는 패턴을 찾지 못합니다. 두 번째 및 세 번째 줄에 따라서 모든 텍스트를까지 `*/`, 주석으로 처리로 처리 됩니다.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   컴파일러가이 설명에 다음 두 가지 이유로 패턴을 찾지 못합니다. 첫째, 일관 된 수의 별표 앞에 공백으로 시작 하는 선이 없습니다 되었습니다. 둘째, 다섯 번째 줄이 공백과 일치하지 않는 탭으로 시작합니다. 따라서 모든 텍스트 될 때까지 두 번째 줄에서는 `*/` 주석으로 처리로 처리 됩니다.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)