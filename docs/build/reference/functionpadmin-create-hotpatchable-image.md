---
title: "/FUNCTIONPADMIN(핫 패치 가능 이미지 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/functionpadmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FUNCTIONPADMIN 링커 옵션"
  - "-FUNCTIONPADMIN 링커 옵션"
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /FUNCTIONPADMIN(핫 패치 가능 이미지 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

핫 패치 가능한 이미지를 준비합니다.  
  
## 구문  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `space`\(선택적 요소\)  
 각 함수의 시작 부분에 추가할 안쪽 여백의 크기 5, 6 또는 16. x 86 x 64 이미지 여백 5 바이트 6 바이트를 필요로 하 고 이미지 Itanium 프로세서 제품군에 대 한 빌드 요구 각 함수의 시작 부분에 16 바이트 차지 합니다.  
  
 기본적으로 컴파일러는 이미지의 컴퓨터 형식을 기준으로 이미지에 현재 공백의 양을 추가합니다.  
  
 링커에서 핫 패치할 수 있는 이미지를 생성하려면 .obj 파일을 [\/hotpatch\(핫 패치 가능 이미지 만들기\)](../../build/reference/hotpatch-create-hotpatchable-image.md)로 컴파일해야 합니다.  
  
 cl.exe를 한 번 실행하여 이미지를 컴파일하고 링크하는 경우 **\/hotpatch**를 사용하면 **\/functionpadmin**이 자동으로 적용됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)