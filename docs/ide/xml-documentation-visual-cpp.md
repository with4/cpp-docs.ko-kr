---
title: "XML 문서 (Visual c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17853a43d3a94be779b659b0da825467fa66f61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="xml-documentation-visual-c"></a>XML 문서(Visual C++)
Visual c + +에서 주석.xml 파일에 처리할 수 있는 소스 코드를 추가할 수 있습니다. 이 파일을 코드의 클래스에 대 한 설명서를 만드는 프로세스에 대 한 입력 될 수 있습니다.  
  
 Visual c + + 코드 파일에서 XML 문서 주석 메서드 또는 형식 정의 이전 직접 있어야 합니다. 주석은은 다음과 같은 시나리오에서 Intellisense QuickInfo 데이터 팁을 채우는 데 사용할 수 있습니다.  
  
1.  해당 하는.winmd 파일에 있는 코드를 Windows 런타임 구성 요소로 컴파일할 때  
  
2.  현재 프로젝트에 소스 코드가 포함 된 경우  
  
3.  해당 형식 선언 및 구현이 동일한 헤더 파일에 있는 라이브러리의  
  
> [!NOTE]
>  현재 릴리스에서 템플릿 또는 템플릿 형식 (예를 들어 템플릿으로 매개 변수를 사용 하는 함수) 들어 있는 모든 코드 주석 처리 되지 않습니다. 이러한 메모 추가 정의 되지 않은 동작이 발생 합니다.  
  
 문서 주석을 사용 하 여.xml 파일을 만드는 방법에 내용은 다음 항목을 참조 하십시오.  
  
|추가 정보|보기|  
|---------------------------|---------|  
|사용 하는 컴파일러 옵션|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|설명서의 기능을 사용 하는 일반적으로 제공 하는 데 태그|[문서 주석에 대한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|코드의 구문을 식별 하기 위해 컴파일러에서 생성 하는 ID 문자열|[.Xml 파일 처리](../ide/dot-xml-file-processing.md)|  
|문서 태그를 구분 하는 방법|[Visual C++ 문서 태그의 구분 기호](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|하나 이상의.xdc 파일에서.xml 파일을 생성 합니다.|[XDCMake 참조](../ide/xdcmake-reference.md)|  
|Visual Studio 기능 영역에 그대로 XML에 대 한 정보 링크를 연결 됨|[Visual Studio의 XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 특수 문자를 XML 문서 주석의 텍스트에 포함 해야 할 경우 XML 엔터티 또는 CDATA 섹션을 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)