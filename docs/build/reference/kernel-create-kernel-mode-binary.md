---
title: -커널 (만들 커널 모드 이진) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /kernel
- /kernel-
dev_langs:
- C++
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbae275e751287464e4bf1637ee21aff77fb697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel(커널 모드 이진 만들기)
Windows 커널에서 실행할 수 있는 이진 파일을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
/kernel[-]  
```  
  
## <a name="arguments"></a>인수  
 **/kernel**  
 현재 프로젝트에 코드를 컴파일하여 커널 모드에서 실행 되는 코드에만 적용 되는 c + + 언어 규칙의 집합을 사용 하 여 연결 합니다.  
  
 **/kernel-**  
 현재 프로젝트에 코드를 컴파일하여 커널 모드에서 실행 되는 코드에만 적용 되는 c + + 언어 규칙을 사용 하지 않고 연결 합니다.  
  
## <a name="remarks"></a>설명  
 없는 `#pragma` 이 옵션을 제어와 동일 합니다.  
  
 지정 하는 **/kernel** 옵션을 컴파일러와 링커 커널 모드에서 허용 되는 언어 기능을 조정 하 고 있는지 확인 하기는 런타임 불안정을 방지 하기 위해 충분 한 역대 해야 하는 명령 커널 모드 c + +에 고유 합니다. 이 커널 모드에서 중단 하는 c + + 언어 기능의 사용은 허용 하 고 잠재적으로 장치를 중단 해야 하지만 비활성화할 수 없습니다는 c + + 언어 기능에 대 한 경고를 제공 하 여 수행 됩니다.  
  
 **/kernel** 옵션 컴파일러와 링커 둘 다 빌드 단계를 적용 하 고 프로젝트 수준에서 설정 됩니다. 전달 된 **/kernel** 스위치는 결과 이진, 연결 후에 로드 되어야 할 Windows 커널의 컴파일러에 알립니다. 컴파일러는 커널 호환 되는 하위 집합에 대 한 c + + 언어 기능의 스펙트럼을 좁혀집니다.  
  
 다음 표에서 컴파일러의 한 변경 내용은 때 **/kernel** 지정 됩니다.  
  
|동작 유형|**/kernel** 동작|  
|-------------------|---------------------------|  
|C++ 예외 처리|사용 하지 않습니다. 모든 인스턴스는 `throw` 및 `try` 키워드는 컴파일러 오류를 내보냅니다 (예외 사양을 제외한 `throw()`). 더 **/EH** 옵션은 호환 **/kernel**를 제외 하 고 **/EH-** 합니다.|  
|RTTI|사용 하지 않습니다. 모든 인스턴스는 `dynamic_cast` 및 `typeid` 키워드 하지 않는 한 컴파일러 오류 내보낼 `dynamic_cast` 정적으로 사용 됩니다.|  
|`new` 및 `delete`|명시적으로 정의 해야는 `new()` 또는 `delete()` 연산자; 컴파일러도 아니고 런타임에서 default 정의 제공 합니다.|  
  
 호출 규칙을 사용자 지정은 [/GS](../../build/reference/gs-buffer-security-check.md) 빌드 옵션 및 모든 최적화 사용 하는 경우 허용 되는 **/kernel** 옵션입니다. 인라인 처리의 영향을 받지 주로 **/kernel**와 동일한 의미 체계는 컴파일러에서 적용 합니다. 다음 사항을 확인 하려면는 `__forceinline` 인라이닝 한정자가 허용 해야 하며 해당 경고, [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 특정 시기를 알 수 있도록 활성화 `__forceinline` 함수는 인라인 하지 않습니다.  
  
 컴파일러가 전달 하는 경우는 **/kernel** 스위치,이 미리 정의 지정 되어 있는 전처리기 매크로 `_KERNEL_MODE` 있고 값 **1**합니다. 이 조건에 따라 사용자 모드 또는 커널 모드 실행 환경을 인지에 따라 코드를 컴파일하는 데 사용할 수 있습니다. 예를 들어 다음 코드 커널 모드 실행을 위해 컴파일될 때 클래스는 페이징할 메모리 세그먼트에 해야 함을 지정 합니다.  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
   // ...
};  
```  
  
 일부 대상 아키텍처에서 다음과 같은 조합 및 **/arch** 옵션을 함께 사용 될 때 오류가 생성 **/kernel**:  
  
-   **/arch: {SSE&#124;SSE2&#124;AVX}** x86에서 지원 되지 않습니다. 만 **/arch:IA32** 를 사용할 수 **/kernel** x86 합니다.  
  
-   **/arch: avx** 지원 되지 않는 **/kernel** x64 합니다.  
  
 사용 구축 **/kernel** 전달 **/kernel** 링커에 합니다. 그녀는 링커 동작에 미치는 영향을입니다.  
  
-   증분 링크를 사용할 수 없습니다. 추가 하는 경우 **/incremental** 명령줄을 사용 하면 링커에서이 치명적인 오류:  
  
     **링크: 심각한 오류 LNK1295: '/ 증분'와 호환 되지 않는 ' / 커널 ' 사양입니다. '/ 증분' 없이 연결**  
  
-   링커 검사 것 수 있는 된 컴파일 확인 사용 하 여 각 개체 파일 (또는 정적 라이브러리에서 모든 포함된 보관 멤버)는 **/kernel** 옵션 아니었습니다. 이 조건을 충족 하는 모든 인스턴스를 링커 성공적으로 연결 있지만는 다음 표에 나와 있는 것 처럼 경고를 실행할 수 있습니다.  
  
    ||**/kernel** obj|**/kernel-** obj, MASM obj 또는 cvtresed|혼합 **/kernel** 및 **/kernel-** objs|  
    |-|----------------------|-----------------------------------------------|-------------------------------------------------|  
    |**링크 /kernel**|예|예|예, LNK4257 경고 있음|  
    |**링크**|예|예|예|  
  
     **/Kernel; 컴파일되지 LNK4257 연결 개체 이미지가 실행 되지 않습니다.**  
  
 **/kernel** 옵션 및 **/driver** 옵션 독립적으로 작동 하 고 둘 다에 영향을 다른 합니다.  
  
### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>Visual Studio에서 /kernel 컴파일러 옵션을 설정 하려면  
  
1.  열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  에 **추가 옵션** 상자에서 추가 `/kernel` 또는 `/kernel-`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)