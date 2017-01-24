---
title: "XML 문서(Visual C++) | Microsoft Docs"
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
  - "/// C++ 문서의 구분 기호"
  - "주석, C++ 소스 코드 파일"
  - "XML 문서"
  - "XML, 소스 코드의 문서 주석"
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XML 문서(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+.xml 파일로 처리 되는 소스 코드에 주석을 추가할 수 있습니다.  이 파일은 다음 코드에서 클래스에 대 한 설명서를 만드는 프로세스는 입력 수 없습니다.  
  
 Visual C\+\+ 코드 파일에서 XML 문서 주석은 메서드 또는 형식을 정의 하기 전에 직접에 있어야 합니다.  메모는 Intellisense QuickInfo 데이터 팁 다음 시나리오에서를 채우는 데 사용할 수 있습니다.  
  
1.  때 코드가 Windows 런타임 구성 요소로 포함 된.winmd 파일을 컴파일 되었습니다  
  
2.  현재 프로젝트의 소스 코드를 포함 하는 경우  
  
3.  라이브러리에 있는 형식 선언과 구현을 같은 헤더 파일에 있는  
  
> [!NOTE]
>  현재 릴리스에서 코드 주석에서 템플릿 또는 템플릿 형식 \(예: 매개 변수로 템플릿에 사용 함수\)를 포함 하는 아무 것도 처리 되지 않습니다.  이러한 주석 추가 정의 되지 않은 동작이 발생 합니다.  
  
 문서 주석으로.xml 파일을 만드는 자세한 내용은 다음 항목을 참조 하십시오.  
  
|추가 정보|참조|  
|-----------|--------|  
|사용 하는 컴파일러 옵션|[\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|설명서에 사용 되는 기능 태그 일반적으로 제공할 수 있습니다.|[문서 주석에 대한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|컴파일러에서 생성할 코드의 구문을 식별 하는 ID 문자열|[.Xml 파일을 처리합니다.](../ide/dot-xml-file-processing.md)|  
|문서 태그를 구분 하는 방법|[Visual C\+\+ 문서 태그에 대 한 구분 기호](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|하나 이상의.xdc 파일에서.xml 파일을 생성합니다.|[XDCMake 참조](../ide/xdcmake-reference.md)|  
|XML에 대 한 정보는 링크를 Visual Studio 기능 영역에 관련 된|[Visual Studio XML](../Topic/XML%20Tools%20in%20Visual%20Studio.md)|  
  
 문서 주석의 텍스트에 XML 특수 문자를 삽입 하는 경우 XML 엔터티 또는 CDATA 섹션을 사용 해야 합니다.  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)