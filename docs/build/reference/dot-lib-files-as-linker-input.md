---
title: "링커 입력 파일로 사용하는 .Lib 파일 | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.AdditionalDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib 파일"
  - "COFF 파일, 가져오기 라이브러리"
  - "기본 라이브러리[C++]"
  - "기본 라이브러리[C++], 링커 출력"
  - "기본값[C++], 라이브러리"
  - "가져오기 라이브러리, 링커 파일"
  - "라이브러리[C++], 링커 입력 파일로 사용하는 .lib 파일"
  - "링크[C++], OMF 라이브러리"
  - "OMF 라이브러리"
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Lib 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK에서는 대개 확장명이 .lib인 COFF 표준 라이브러리와 COFF 가져오기 라이브러리를 사용합니다.  표준 라이브러리에는 개체가 포함되어 있으며 LIB 도구로 만들어집니다.  가져오기 라이브러리에는 다른 프로그램에 있는 내보내기에 대한 정보가 포함되어 있으며, 내보내기가 포함된 프로그램을 빌드 할 때 LINK를 사용하거나 LIB 도구를 사용하여 만듭니다.  LIB를 사용하여 표준 또는 가져오기 라이브러리를 만드는 방법에 대한 자세한 내용은 [LIB 참조](../../build/reference/lib-reference.md)를 참조하십시오.  LINK를 사용하여 가져오기 라이브러리를 만드는 방법에 대한 자세한 내용은 [\/DLL](../../build/reference/dll-build-a-dll.md) 옵션을 참조하십시오.  
  
 라이브러리는 파일 이름 인수나 기본 라이브러리로 LINK에 지정됩니다.  LINK에서는 명령줄에 지정된 라이브러리에서 먼저 검색한 다음 [\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) 옵션으로 지정된 기본 라이브러리와 .obj 파일에 지정된 기본 라이브러리에서 차례로 검색하는 방법으로 외부 참조를 확인합니다.  경로가 라이브러리 이름과 함께 지정되면 LINK에서는 해당 디렉터리에서 라이브러리를 찾습니다.  지정된 경로가 없으면 LINK에서는 먼저 LINK가 실행된 디렉터리에서 찾은 다음 LIB 환경 변수로 지정된 디렉터리에서 찾습니다.  
  
### 개발 환경에서 .lib 파일을 링커 입력 파일로 추가하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **추가 종속성** 속성을 수정합니다.  
  
### .lib 파일을 프로그래밍 방식으로 링커 입력 파일로 추가하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalDependencies%2A>를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 .lib 파일을 빌드하고 사용하는 방법을 보여 줍니다. 첫 번째 코드 파일:  
  
```  
// lib_link_input_1.cpp  
// compile with: /LD  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
## 예제  
 두 번째 코드 파일:  
  
```  
// lib_link_input_2.cpp  
// compile with: /EHsc lib_link_input_1.lib  
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
  **213**   
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)