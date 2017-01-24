---
title: "/link(옵션을 링커로 전달) | Microsoft Docs"
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
  - "/link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/link 컴파일러 옵션[C++]"
  - "cl.exe 컴파일러[C++], 링커에 옵션 전달"
  - "link 컴파일러 옵션[C++]"
  - "-link 컴파일러 옵션[C++]"
  - "링커[C++], 옵션 전달"
  - "링커에 옵션 전달"
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /link(옵션을 링커로 전달)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 링커 옵션을 링커에 전달할 수 있습니다.  
  
## 구문  
  
```  
/link linkeroptions  
```  
  
## 인수  
 `linkeroptions`  
 링커로 전달할 링커 옵션입니다.  
  
## 설명  
 **\/link** 옵션과 이 옵션의 링커 옵션은 파일 이름과 CL 옵션 뒤에 사용해야 합니다.  **\/link**와 `linkeroptions` 사이에는 공백이 하나 있어야 합니다.  자세한 내용은 [링커 옵션 설정](../../build/reference/setting-linker-options.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  링커 속성 페이지를 클릭합니다.  
  
4.  하나 이상의 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)