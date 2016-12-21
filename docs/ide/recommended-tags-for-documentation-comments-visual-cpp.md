---
title: "문서 주석에 대한 권장 태그(Visual C++) | Microsoft Docs"
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
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 문서 주석에 대한 권장 태그(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 컴파일러 코드에서 문서 주석을 처리 하는 각 컴파일 대상에 대해.xdc 파일을 만듭니다 및 xdcmake.exe는.xdc 파일을.xml 파일로 처리 합니다.  문서를 만들 수 있는.xml 파일 처리 사용자의 사이트에서 구현 해야 하는 세부적인 사항입니다.  
  
 태그 형식 등과 같은 구문에서 처리 및 형식 멤버입니다.  
  
 태그 형식 또는 멤버 바로 앞에 있어야 합니다.  
  
> [!NOTE]
>  문서 주석은 네임 스페이스 또는 선 정의 대 한 속성 및 이벤트를 적용할 수 없습니다. 문서 주석은 클래스의 선언에 해야합니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리합니다.  다음 태그 사용자 설명서에서 자주 사용 하는 기능을 제공합니다.  
  
||||  
|-|-|-|  
|[\<c\>](../ide/c-visual-cpp.md)|[\<code\>](../ide/code-visual-cpp.md)|[\<example\>](../ide/example-visual-cpp.md)|  
|[\<exception\>](../ide/exception-visual-cpp.md)1|[\<include\>](../ide/include-visual-cpp.md)1|[\<list\>](../ide/list-visual-cpp.md)|  
|[\<para\>](../ide/para-visual-cpp.md)|[\<param\>](../ide/param-visual-cpp.md)1|[\<paramref\>](../ide/paramref-visual-cpp.md)1|  
|[\<permission\>](../ide/permission-visual-cpp.md)1|[\<remarks\>](../ide/remarks-visual-cpp.md)|[\<returns\>](../ide/returns-visual-cpp.md)|  
|[\<see\>](../ide/see-visual-cpp.md)1|[\<seealso\>](../ide/seealso-visual-cpp.md)1|[\<summary\>](../ide/summary-visual-cpp.md)|  
|[\<value\>](../ide/value-visual-cpp.md)|||  
  
 1.  컴파일러가 구문을 확인 합니다.  
  
 현재 릴리스에서 Visual C\+\+ 컴파일러 지원 하지 않는 `<paramref>`, 다른 Visual Studio 컴파일러에서 지 원하는 태그.  Visual C\+\+ 수도 지원 `<paramref>` 는 차후 릴리스에서.  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)