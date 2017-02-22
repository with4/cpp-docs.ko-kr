---
title: "/Og(전역 최적화) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GlobalOptimizations"
  - "/og"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Og 컴파일러 옵션[C++]"
  - "자동 레지스터 할당"
  - "공용 부분식 제거"
  - "전역 최적화 컴파일러 옵션[C++]"
  - "루프 구조, 최적화"
  - "Og 컴파일러 옵션[C++]"
  - "-Og 컴파일러 옵션[C++]"
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Og(전역 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로컬 및 전역 최적화, 자동 레지스터 할당 및 루프 최적화를 제공합니다.  사용되지 않습니다.  
  
## 구문  
  
```  
/Og  
```  
  
## 설명  
 사용할 수 있는 최적화는 다음과 같습니다.  
  
-   로컬 및 전역 공통 부분식 제거  
  
     이 최적화에서는 공통 부분식의 값이 한 번 계산됩니다.  다음 예제에서 세 식 사이에 `b`와 `c`의 값이 변경되지 않으면 컴파일러는 `b + c` 계산을 임시 변수에 할당하여 이 변수를 `b + c` 대신 사용할 수 있습니다.  
  
    ```  
    a = b + c;  
    d = b + c;  
    e = b + c;  
    ```  
  
     로컬 공통 부분식 최적화의 경우에는 컴파일러가 짧은 코드 섹션에서 공통 부분식을 검사합니다.  전역 공통 부분식 최적화의 경우에는 컴파일러가 전체 함수에서 공통 부분식을 검색합니다.  
  
-   자동 레지스터 할당  
  
     이 최적화를 사용하면 컴파일러에서 자주 사용하는 변수와 부분식을 레지스터에 저장할 수 있습니다. `register` 키워드는 무시됩니다.  
  
-   루프 최적화  
  
     이 최적화는 루프 본문에서 불변 부분식을 제거합니다.  최적 루프에는 루프를 실행할 때마다 값이 변경되는 식만 포함됩니다.  다음 예제의 루프 본문에서 `x + y` 식은 변경되지 않습니다.  
  
    ```  
    i = -100;  
    while( i < 0 ) {  
        i += x + y;  
    }  
    ```  
  
     최적화하면 `x + y` 식은 루프가 실행될 때마다 계산되지 않고 한 번만 계산됩니다.  
  
    ```  
    i = -100;  
    t = x + y;  
    while( i < 0 ) {  
        i += t;  
    }  
    ```  
  
     루프 최적화는 컴파일러에서 별칭을 사용할 수 없는 경우에 훨씬 더 효율적입니다. 이는 [\_\_restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md) 또는 [restrict](../../cpp/restrict.md)를 사용하여 설정합니다.  
  
    > [!NOTE]
    >  `optimize` pragma에 `g` 옵션을 사용하면 함수별로 전역 최적화를 활성화하거나 비활성화할 수 있습니다.  
  
 **\/Og**를 사용하여 명명된 반환 값 최적화를 활성화할 수도 있습니다. 이렇게 하면 반환 값을 기반으로 스택의 복사 생성자와 소멸자가 제거됩니다.  자세한 내용은 [\/O1, \/O2\(크기 최소화, 속도 최대화\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)를 참조하십시오.  
  
 자세한 내용은 [내장 함수 만들기\(\/Oi\)](../../build/reference/oi-generate-intrinsic-functions.md) 및 [최대 최적화\(\/Ox\)](../../build/reference/ox-full-optimization.md)를 참조하십시오.  
  
 **\/Og**는 사용되지 않습니다. [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 **\/O2**를 사용하십시오.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)