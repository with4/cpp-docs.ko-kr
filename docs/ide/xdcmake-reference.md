---
title: "XDCMake 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xdcmake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "xdcmake 프로그램"
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XDCMake 참조
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

xdcmake.exe는.xdc 파일을.xml 파일로 컴파일되는 프로그램입니다.  소스 코드를 컴파일할 때.xdc 파일 각 소스 코드 파일을 Visual C\+\+ 컴파일러에서 만든  [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) 및 소스 코드 파일에 문서 주석을 XML 태그로 마크업이 있는 경우.  
  
### Visual Studio 개발 환경에서 xdcmake.exe를 사용 하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  열려 있는  **구성 속성** 폴더입니다.  
  
3.  클릭 하 여  **XML 문서 주석** 속성 페이지.  
  
> [!NOTE]
>  개발 환경 \(속성 페이지\)에서 xdcmake.exe를 사용 하는 경우 명령줄에서 xdcmake.exe 옵션 옵션에서 다.  Xdcmake.exe를 사용 하 여 개발 환경에서에 대 한 자세한 내용은 [XML 문서 생성기 도구 속성 페이지](../ide/xml-document-generator-tool-property-pages.md).  
  
## 구문  
 xdcmake`input_filename options`  
  
## 매개 변수  
 다음은 각 문자에 대한 설명입니다.  
  
 `input_filename`  
 Xdcmake.exe 입력으로 사용 되는.xdc 파일의 파일 이름입니다.  .Xdc 파일을 하나 이상 지정 하거나 \*.xdc를 사용 하 여 현재 디렉터리에 있는 모든.xdc 파일을 사용 합니다.  
  
 `options`  
 0 개 이상의 다음 중:  
  
|옵션|설명|  
|--------|--------|  
|\/?, \/help|Xdcmake.exe에 대 한 도움말을 표시 합니다.|  
|\/assembly:*파일 이름*|\<assembly\>의 값을 지정할 수 있습니다. .xml 파일에 태그입니다.  기본적으로 \<assembly\>의 값 태그를 사용 하는.xml 파일의 파일 이름입니다.|  
|\/nologo|저작권 메시지를 표시하지 않습니다.|  
|\/out:*파일 이름*|.Xml 파일의 이름을 지정할 수 있습니다.  기본적으로,.xml 파일의 이름을 xdcmake.exe가 처리 첫 번째.xdc 파일의 이름입니다.|  
  
## 설명  
 Visual Studio xdcmake.exe는 프로젝트를 빌드할 때 자동으로 호출 합니다.  명령줄에서 xdcmake.exe를 호출할 수도 있습니다.  
  
 볼  [문서 주석에 대 한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) 에 대 한 자세한 내용은 소스 코드 파일에 문서 주석을 추가 합니다.  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)