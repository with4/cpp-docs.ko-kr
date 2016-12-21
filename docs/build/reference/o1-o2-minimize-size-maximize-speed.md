---
title: "/O1, /O2(크기 최소화, 속도 최대화) | Microsoft Docs"
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
  - "/o2"
  - "/o1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/O1 컴파일러 옵션[C++]"
  - "/O2 컴파일러 옵션[C++]"
  - "빠른 코드"
  - "속도 최대화 컴파일러 옵션[C++]"
  - "크기 최소화 컴파일러 옵션[C++]"
  - "O1 컴파일러 옵션[C++]"
  - "-O1 컴파일러 옵션[C++]"
  - "O2 컴파일러 옵션[C++]"
  - "-O2 컴파일러 옵션[C++]"
  - "작은 코드"
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /O1, /O2(크기 최소화, 속도 최대화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일의 크기와 속도에 영향을 주는 미리 정의된 옵션 집합을 선택합니다.  
  
## 구문  
  
```  
/O1  
/O2  
```  
  
## 설명  
 다음 표에서는 **\/O1** 및 **\/O2**에 대해 설명합니다.  
  
|옵션|포함되는 옵션|주석|  
|--------|-------------|--------|  
|**\/O1**\(크기 최소화\)|**\/Og \/Os \/Oy \/Ob2 \/Gs \/GF \/Gy**|대부분의 경우에 가장 작은 코드를 만듭니다.|  
|**\/O2**\(속도 최대화\)|**\/Og \/Oi \/Ot \/Oy \/Ob2 \/Gs \/GF \/Gy**|대부분의 경우 속도가 가장 빠른 코드를 만듭니다. 릴리스 빌드의 기본 설정입니다.|  
  
 **\/O1** 및 **\/O2**를 사용하면 반환 값을 기반으로 스택에서 복사 생성자와 소멸자를 삭제하는 명명된 반환 값 최적화도 활성화됩니다.  다음 샘플을 참고하십시오.  `Test` 함수는 복사 생성자나 소멸자를 만들지 않습니다.  생성자에 출력 문을 추가하면 프로그램을 실행할 때 소멸자와 복사 생성자에 미치는 명명된 반환 값 최적화의 영향을 확인할 수 있습니다.  자세한 내용은 [명명 된 반환 값 최적화 Visual C\+\+ 2005](http://go.microsoft.com/fwlink/?linkid=131571)를 참조하세요.  
  
```  
// O1_O2_NRVO.cpp  
// compile with: /O1  
struct A {  
   A() {}  
   ~A() {}  
   A(const A& aa) {}  
};  
  
A Test() {  
   A a;  
   return a;  
}  
int main() {  
   A aa;  
   aa = Test();  
}  
```  
  
 **x86 전용**  
  
 이 옵션에는 프레임 포인터 생략 옵션\([\/Oy](../../build/reference/oy-frame-pointer-omission.md)\) 사용이 포함되어 있습니다.  
  
 **END x86 Specific**  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **최적화** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/O 옵션\(코드 최적화\)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)