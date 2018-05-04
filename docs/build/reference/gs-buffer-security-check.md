---
title: -GS (버퍼 보안 검사) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
- /GS
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa1204a6959121b3f6280433c0414f81c038548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="gs-buffer-security-check"></a>/GS(버퍼 보안 검사)  
  
버퍼 오버런은 함수의 반환 주소, 예외 처리기 주소 또는 특정 형식의 매개 변수 덮어쓰기을 검색 합니다. 버퍼 오버런는 해커 버퍼 크기 제한을 적용 하지 않는 코드를 악용 하는 데 사용 하는 방법입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GS[-]  
```  
  
## <a name="remarks"></a>설명  
  
**/GS** 는 기본적으로 설정 합니다. 사용 하 여 응용 프로그램을 없는 보안 위험에 노출 하려는 경우 **/GS-** 합니다. 에 대 한 자세한 내용은 **/GS**, 참조 [컴파일러 보안 검사의 깊이](http://go.microsoft.com/fwlink/p/?linkid=7260)합니다. 버퍼 오버런 감지가 억제 하는 방법에 대 한 자세한 내용은 참조 [safebuffer](../../cpp/safebuffers.md)합니다.  
  
## <a name="security-checks"></a>보안 검사  
  
을 버퍼 오버런 문제 수 있다고 간주 컴파일러에서 인식 하는 함수에는 스택에서 반송 주소 앞에 공간을 할당 합니다. 함수 시작 할당 된 공간와 함께 로드 되는 *보안 쿠키* 모듈 로드 시 한 번 계산 되는 합니다. 함수가 종료 하 고 64 비트 운영 체제에서 프레임을 해제 하는 동안 쿠키의 값은 여전히 동일 있는지 확인 하는 도우미 함수 라고 합니다. 다른 값을 스택의 덮어쓰기 발생 했을 수 있는지를 나타냅니다. 다른 값이 검색 되 면 프로세스가 종료 됩니다.  
  
## <a name="gs-buffers"></a>GS 버퍼  
  
버퍼 오버런 보안 검사가 수행 됩니다는 *GS 버퍼*합니다. GS 버퍼는이 중 하나일 수 있습니다.  
  
-   4 바이트 보다 큰 배열 두 개 이상의 요소를 가지 며 요소 형식이 포인터 형식이 아닌  
  
-   필요에 따라 크기가 8 바이트 보다 큰 및 없는 포인터를 포함 하는 데이터 구조입니다.  
  
-   사용 하 여 할당 된 버퍼는 [_alloca](../../c-runtime-library/reference/alloca.md) 함수입니다.  
  
-   클래스 또는 GS 버퍼를 포함 하는 구조체.  
  
예를 들어 다음 문은 GS 버퍼를 선언 합니다.  
  
```cpp  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
그러나 다음 문에서 GS 버퍼를 선언 하지 않습니다. 처음 두 개의 선언 포인터 형식의 요소를 포함 합니다. 세 번째와 네 번째 문은 필요에 따라 크기가 너무 작습니다. 배열을 선언 합니다. 5 번째 문에 x86 플랫폼은 8 바이트 이상 구조를 필요에 따라 크기가 선언 합니다.  
  
```cpp  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## <a name="initialize-the-security-cookie"></a>보안 쿠키를 초기화 합니다.  
  
**/GS** 컴파일러 옵션을 사용 하려면 쿠키를 사용 하는 함수를 실행 하기 전에 보안 쿠키를 초기화 해야 합니다. EXE 또는 DLL에 대 한 항목에 보안 쿠키를 즉시 초기화 되어야 합니다. VCRuntime 기본 진입점을 사용 하는 경우 자동으로 수행 됩니다이: mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup, 또는 _DllMainCRTStartup 합니다. 호출 하 여 보안 쿠키를 수동으로 초기화 해야 합니다는 대체 진입점을 사용 하는 경우 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md)합니다.  
  
## <a name="what-is-protected"></a>보호 되는 정보  
  
**/GS** 컴파일러 옵션은 다음 항목을 보호 합니다.  
  
-   함수 호출의 반환 주소입니다.  
  
-   함수에 대 한 예외 처리기의 주소입니다.  
  
-   취약 한 함수 매개 변수입니다.  
  
모든 플랫폼에서 **/GS** 반송 주소에 대 한 버퍼 오버런 검색을 시도 합니다. 버퍼 오버런 공격 x86 및 x64 스택에 함수 호출의 반환 주소를 저장 하는 호출 규칙을 사용 하 여 같은 플랫폼에 보다 쉽게 됩니다.  
  
컴파일러는 함수에 예외 처리기를 사용 하 여 x86, 예외 처리기의 주소를 보호 하기 위해 보안 쿠키를 추가 합니다. 쿠키는 프레임을 해제 하는 동안 검사 됩니다.  
  
**/GS** 보호 *취약 한 매개 변수가* 을 함수로 전달 합니다. 이러한 매개 변수는 C 구조체 (c + + POD 형식)는 포인터 또는 GS 버퍼를 포함 하는 c + + 참조, 포인터.  
  
이러한 매개 변수는 쿠키 및 지역 변수가 앞에 할당 됩니다. 버퍼 오버런 이러한 매개 변수를 덮어쓸 수 있습니다. 및 이러한 매개 변수를 사용 하는 함수에 코드 함수를 반환 하 고 보안 검사가 수행 됩니다 전에 공격을 받을 수 있습니다. 이러한 위험을 최소화 하려면 컴파일러 함수 프롤로그 하는 동안 취약 한 매개 변수가의 복사본을 만들고 버퍼 저장소 영역 아래에 배치 합니다.  
  
컴파일러는 다음과 같은 경우에 취약 한 매개 변수가의 복사본을 만들지 않습니다.  
  
-   GS 버퍼를 포함 하지 않는 함수입니다.  
  
-   최적화 ([/O 옵션](../../build/reference/o-options-optimize-code.md))을 사용할 수 없습니다.  
  
-   가변 인수 목록 (...)가 있는 함수입니다.  
  
-   로 표시 된 함수 [naked](../../cpp/naked-cpp.md)합니다.  
  
-   첫 번째 문에서 인라인 어셈블리 코드를 포함 하는 함수입니다.  
  
-   매개 변수는 버퍼 오버런이 발생 될 가능성이 낮습니다 하는 방식 으로만 사용 됩니다.  
  
## <a name="what-is-not-protected"></a>보호 되지 않는 정보  
  
**/GS** 컴파일러 옵션 모든 버퍼 오버런 보안 공격 으로부터 보호 되지 않습니다. 예를 들어 개체에 있는 버퍼와 vtable을 했다면 버퍼 오버런이 vtable를 손상 될 수 있습니다.  
  
사용 하는 경우에 **/GS**, 항상 버퍼 오버런이 없는 안전한 코드를 작성 하려고 합니다.  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.  
  
     자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  에 **속성 페이지** 대화 상자를 클릭는 **C/c + +** 폴더입니다.  
  
3.  클릭는 **코드 생성** 속성 페이지.  
  
4.  수정 된 **버퍼 보안 검사** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
  
이 샘플에는 버퍼를 오버런 됩니다. 이렇게 하면 런타임 시 실패 하도록 응용 프로그램.  
  
```C  
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
  
## <a name="see-also"></a>참고 항목  
  
[컴파일러 옵션](../../build/reference/compiler-options.md)   
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)