---
title: "/Zg(함수 프로토타입 생성) | Microsoft Docs"
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
  - "/zg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zg 컴파일러 옵션[C++]"
  - "함수 프로토타입, 함수 프로토타입 생성 컴파일러 옵션"
  - "함수 프로토타입 생성 컴파일러 옵션"
  - "Zg 컴파일러 옵션[C++]"
  - "-Zg 컴파일러 옵션[C++]"
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zg(함수 프로토타입 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제거됩니다. 소스 파일에 정의된 각 함수에 대한 함수 프로토타입을 만들지만 소스 파일을 컴파일하지 않습니다.  
  
## 구문  
  
```  
/Zg  
```  
  
## 설명  
 이 컴파일러 옵션은 더 이상 사용할 수 없습니다. Visual C\+\+ 2015에서 제거되었습니다. 이 페이지는 이전 버전의 Visual C\+\+ 사용자를 위해 남아 있습니다.  
  
 함수 프로토타입에는 함수 반환 형식 및 인수 형식 목록이 포함되어 있습니다. 인수 형식 목록은 함수의 정식 매개 변수 형식에서 만들어집니다. 소스 파일에 이미 있는 모든 함수 프로토타입은 무시됩니다.  
  
 프로토타입 목록은 표준 출력에 기록됩니다. 이 목록은 함수의 실제 인수 및 정식 매개 변수가 호환되는지 확인하는 데 유용합니다. 표준 출력을 파일로 리디렉션하여 목록을 저장할 수 있습니다. 그런 다음 **\#include**를 사용하여 함수 프로토타입 목록을 소스 파일의 일부로 만들 수 있습니다. 그러면 컴파일러가 인수 형식 검사를 수행합니다.  
  
 **\/Zg** 옵션을 사용하고 프로그램에 구조체, 열거형 또는 공용 구조체 형식\(또는 이러한 형식에 대한 포인터\)이 있는 정식 매개 변수가 포함되는 경우 각 구조체, 열거형 또는 공용 구조체 형식의 선언에 태그\(이름\)가 있어야 합니다. 다음 샘플에서 태그 이름은 `MyStruct`입니다.  
  
```  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **\/Zg**은 사용되지 않습니다. Visual C\+\+ 컴파일러는 이전의 C 스타일 코드에 대한 지원을 제거할 계획입니다. 자세한 내용은 [Visual C\+\+ 2005의 사용되지 않는 컴파일러 옵션](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)