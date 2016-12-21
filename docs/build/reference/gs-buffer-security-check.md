---
title: "/GS(버퍼 보안 검사) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.BufferSecurityCheck"
  - "VC.Project.VCCLCompilerTool.BufferSecurityCheck"
  - "/GS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "버퍼[C++], 버퍼 오버런"
  - "버퍼 오버런, 컴파일러 /GS 스위치"
  - "GS 컴파일러 옵션[C++]"
  - "/GS 컴파일러 옵션[C++]"
  - "보안 확인 컴파일러 옵션[C++]"
  - "-GS 컴파일러 옵션[C++]"
  - "버퍼[C++], 오버런 방지"
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GS(버퍼 보안 검사)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수의 반환 주소, 예외 처리기 주소 또는 특정 형식의 매개 변수를 덮어쓰는 일부 버퍼 오버런을 검색합니다.  버퍼 오버런은 버퍼 크기 제한을 적용하지 않는 코드를 악용하기 위해 해커가 사용하는 기술입니다.  
  
## 구문  
  
```  
/GS[-]  
```  
  
## 설명  
 **\/GS**는 기본적으로 사용됩니다.  응용 프로그램이 보안 위험에 노출되지 않도록 하려면 **\/GS\-**를 사용하는 것이 좋습니다.   **\/GS** 에 대한 자세한 내용은 [Compiler Security Checks In Depth](http://go.microsoft.com/fwlink/?linkid=7260) 를 참조하십시오.  버퍼 오버런 검색을 표시하지 않는 자세한 내용은 [safebuffer](../../cpp/safebuffers.md)를 참조하십시오.  
  
## 보안 검사  
 컴파일러가 버퍼 오버런 문제가 발생할 수 있다고 간주하는 함수에 대해서는 스택에서 반환 주소 앞에 공간을 할당합니다.  함수가 시작될 때, 모듈 로드 시 한 번 계산되는 *보안 쿠키*와 함께 할당된 공간이 로드됩니다.  함수가 종료될 때와 64비트 운영 체제에서 프레임이 해제되는 동안 도우미 함수가 호출되어 쿠키 값이 동일한지 확인합니다.  다른 값은 스택 덮어쓰기가 발생했을 수 있음을 나타냅니다.  다른 값이 검색되는 경우 프로세스가 종료됩니다.  
  
## GS 버퍼  
 *GS 버퍼*에서 버퍼 오버런 보안 검사가 수행됩니다.  GS 버퍼는 다음 중 하나일 수 있습니다.  
  
-   4 바이트 보다 큰 배열에는 두 개 이상의 요소와 포인터 형식이 아닌 요소 형식이 있습니다.  
  
-   크기가 8 바이트 이상이고 포인터를 포함하지 않는 데이터 구조입니다.  
  
-   [\_alloca](../../c-runtime-library/reference/alloca.md) 함수를 사용하여 할당된 버퍼입니다.  
  
-   GS 버퍼를 포함하는 클래스 또는 구조체입니다.  
  
 예를 들어, 다음 문은 GS 버퍼를 선언합니다.  
  
```  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
 그러나, 다음 문은 GS 버퍼를 선언하지 않습니다.  처음 두 개의 선언에 포인터 형식의 요소가 포함되어 있습니다.  세 번째와 네 번째 문은 크기가 너무 작은 배열을 선언합니다.  다섯 번째 문은 x86 플랫폼의 크기가 8바이트를 넘지 않는 구조체를 선언합니다.  
  
```  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## 보안 쿠키를 초기화합니다.  
 **\/GS** 컴파일러 옵션을 사용하려면 쿠키를 사용하는 모든 함수가 실행되기 전에 보안 쿠키를 초기화해야 합니다.  보안 쿠키는 EXE 또는 DLL에 진입할 때 초기화되어야 합니다.  이 초기화는 기본 CRT 진입점\(mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup 또는 \_DllMainCRTStartup\)을 사용하는 경우 자동으로 수행됩니다.  대체 진입점을 사용하는 경우 [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md)를 호출하여 수동으로 보안 쿠키를 초기화해야 합니다.  
  
## 보호되는 정보  
 **\/GS** 컴파일러 옵션은 다음 항목을 보호합니다.  
  
-   함수 호출의 반환 주소입니다.  
  
-   함수에 대한 예외 처리기의 주소입니다.  
  
-   취약한 함수 매개 변수입니다.  
  
 모든 플랫폼에서 **\/GS**는 반환 주소에 대한 버퍼 오버런을 탐지하려고 시도합니다.  함수 호출의 반환 주소를 스택에 저장하는 호출 규칙을 사용하는 x86 및 x64 같은 플랫폼은 버퍼 오버런 공격에 더 취약합니다.  
  
 x86에서 함수가 예외 처리기를 사용하는 경우 컴파일러는 함수의 예외 처리기 주소를 보호하는 보안 쿠키도 추가합니다.  쿠키는 프레임을 해제하는 동안 검사됩니다.  
  
 **\/GS**는 *공격에 취약한 매개 변수*가 함수에 전달되는 경우 이를 보호하는 역할도 합니다.  공격에 취약한 매개 변수로는 포인터 또는 GS 버퍼 등이 포함된 포인터, C\+\+ 참조, C 구조체\(C\+\+ POD 형식\)이 있습니다.  
  
 이러한 매개 변수는 쿠키 및 지역 변수 앞에 할당됩니다.  버퍼 오버런에서는 이러한 매개 변수를 덮어쓸 수 있습니다.  이와 같은 매개 변수를 사용하는 함수의 코드는 함수가 반환하고 보안 검사를 수행하기 전에 공격을 받을 수 있습니다.  이러한 위험을 최소화하기 위해 컴파일러는 함수 프롤로그 도중 공격에 취약한 매개 변수의 복사본을 만들고 이러한 복사본을 버퍼의 저장 영역 아래에 추가합니다.  
  
 다음과 같은 상황에서는 컴파일러가 공격에 취약한 매개 변수에 대한 복사본을 만들지 않습니다.  
  
-   함수에 GS 버퍼가 포함되어 있지 않은 경우  
  
-   최적화\([\/O 옵션](../../build/reference/o-options-optimize-code.md)\)를 사용하지 않는 경우  
  
-   가변 인수 목록\(...\)이 있는 함수.  
  
-   [naked](../../cpp/naked-cpp.md)로 표시된 함수.  
  
-   함수의 첫 번째 문에 인라인 어셈블리 코드가 포함된 경우  
  
-   매개 변수는 버퍼 오버런이 발생해도 공격에 사용될 가능성이 적은 방식으로만 사용됩니다.  
  
## 보호되지 않는 정보  
 **\/GS** 컴파일러 옵션은 모든 버퍼 오버런 보안 공격으로부터 보호하지는 않습니다.  예를 들어, 개체에 버퍼와 vtable이 있는 경우 버퍼 오버런은 vtable을 손상시킬 수 있습니다.  
  
 **\/GS**를 사용하는 경우에도 항상 버퍼 오버런이 없는 보안 코드를 작성하려고 시도하십시오.  
  
#### Visual Studio에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
     자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **속성 페이지** 대화 상자에서 **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **버퍼 보안 검사** 속성을 수정합니다.  
  
#### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>를 참조하십시오.  
  
## 예제  
 이 샘플은 버퍼를 오버런시킵니다.  이렇게 하면 런타임에 응용 프로그램이 실패하게 됩니다.  
  
```  
// compile with: /c /W1  
#include <cstring>  
#include <stdlib.h>  
#pragma warning(disable : 4996)   // for strcpy use  
  
// Vulnerable function  
void vulnerable(const char *str) {  
   char buffer[10];  
   strcpy(buffer, str); // overrun buffer !!!  
  
   // use a secure CRT function to help prevent buffer overruns  
   // truncate string to fit a 10 byte buffer  
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);  
}  
  
int main() {  
   // declare buffer that is bigger than expected  
   char large_buffer[] = "This string is longer than 10 characters!!";  
   vulnerable(large_buffer);  
}  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)