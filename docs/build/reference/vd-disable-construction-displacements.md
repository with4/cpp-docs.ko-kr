---
title: "/vd(생성 치환 비활성화) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vd0 컴파일러 옵션[C++]"
  - "/vd1 컴파일러 옵션[C++]"
  - "/vdn(생성 치환 비활성화) 컴파일러 옵션"
  - "생성자 치환"
  - "생성 치환 비활성화 컴파일러 옵션"
  - "치환 컴파일러 옵션"
  - "vd0 컴파일러 옵션[C++]"
  - "-vd0 컴파일러 옵션[C++]"
  - "vd1 컴파일러 옵션[C++]"
  - "-vd1 컴파일러 옵션[C++]"
  - "vtordisp 필드"
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /vd(생성 치환 비활성화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
/vdn  
```  
  
## 인수  
 `0`  
 vtordisp 생성자\/소멸자 치환 멤버를 사용할 수 없습니다.  이 옵션은 모든 클래스 생성자와 소명자가 실제로 가상 함수를 호출한다고 확신하는 경우에만 선택합니다.  
  
 `1`  
 숨겨진 vtordisp 생성자\/소멸자 치환 멤버의 생성을 활성화합니다.  이 옵션은 기본적으로 선택됩니다.  
  
 `2`  
 생성되고 있는 개체에 [dynamic\_cast 연산자](../../cpp/dynamic-cast-operator.md)를 사용할 수 있도록 합니다.  예를 들어 가상 기본 클래스에서 파생 클래스로 dynamic\_cast를 사용할 수 있습니다.  
  
 가상 함수가 있는 가상 기본의 경우 **\/vd2**는 vtordisp 필드를 추가합니다.  **\/vd1**을 사용해도 충분합니다.  **\/vd2**가 필요한 가장 일반적인 경우는 가상 기본에 있는 유일한 가상 함수가 소멸자인 경우입니다.  
  
## 설명  
 이들 옵션은 가상 기본을 사용하는 C\+\+ 코드에만 적용됩니다.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]는 가상 상속이 사용되는 경우 C\+\+ 생성 치환 지원을 구현합니다.  생성 치환은 가상 기본에서 선언되어 파생된 클래스에서 재정의되는 가상 함수가 추가 파생 클래스의 생성 시에 생성자에서 호출될 때 발생하는 문제를 해결합니다.  
  
 여기서 문제란, 클래스의 가상 기본에 대한 치환과 파생된 클래스에 대한 치환 간의 차이점으로 인해 잘못된 `this` 포인터가 가상 함수에 전달될 수 있다는 것입니다.  이를 해결하기 위해 클래스의 각 가상 기본에 대해 vtordisp 필드라는 단일 생성 치환 조정이 제공됩니다.  
  
 기본적으로, vtordisp 필드는 코드에서 사용자 정의 생성자와 소멸자를 정의하거나 가상 기본의 가상 함수를 재정의할 때마다 사용됩니다.  
  
 이들 옵션은 전체 소스 파일에 영향을 미칩니다.  [vtordisp](../../preprocessor/vtordisp.md)를 사용하여 클래스 단위로 vtordisp 필드를 비활성화한 후 다시 활성화하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)