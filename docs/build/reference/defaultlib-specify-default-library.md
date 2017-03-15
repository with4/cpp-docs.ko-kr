---
title: "/DEFAULTLIB(기본 라이브러리 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.DefaultLibraries"
  - "/defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEFAULTLIB 링커 옵션"
  - "DEFAULTLIB 링커 옵션"
  - "-DEFAULTLIB 링커 옵션"
  - "라이브러리, 목록에 추가"
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /DEFAULTLIB(기본 라이브러리 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEFAULTLIB:library  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *library*  
 외부 참조를 확인할 때 검색할 라이브러리의 이름입니다.  
  
## 설명  
 \/DEFAULTLIB 옵션을 사용하면 LINK에서 참조를 확인할 때 검색하는 라이브러리 목록에 하나의 *library*를 추가할 수 있습니다.  \/DEFAULTLIB로 지정된 라이브러리는 명령줄에서 지정된 라이브러리를 검색한 다음 .obj 파일에 지정된 기본 라이브러리를 검색하기 전에 검색됩니다.  
  
 [모든 기본 라이브러리 무시](../../build/reference/nodefaultlib-ignore-libraries.md)\(\/NODEFAULTLIB\) 옵션을 사용하면 \/DEFAULTLIB:*library*는 무시됩니다.  또한 [라이브러리 무시](../../build/reference/nodefaultlib-ignore-libraries.md)\(\/NODEFAULTLIB:*library*\) 옵션을 사용하는 경우 \/DEFAULTLIB:*library*에도 동일한 *library* 이름이 지정되어 있으면 이 두 번째 옵션은 무시됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
-   이 링커 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다.  라이브러리를 링크 단계에 추가하려면 **입력** 속성 페이지에서 **추가 종속성** 속성을 사용합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)