---
title: "/kernel(커널 모드 이진 만들기) | Microsoft Docs"
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
  - "/kernel"
  - "/kernel-"
dev_langs: 
  - "C++"
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /kernel(커널 모드 이진 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 커널에서 실행 될 수 있는 이진 파일을 만듭니다.  
  
## 구문  
  
```  
/kernel[-]  
```  
  
## 인수  
 **\/kernel**  
 현재 프로젝트에 코드를 컴파일하여 커널 모드에서 실행 되는 코드에 관련 된 c \+ \+ 언어 규칙을 사용하여 연결 합니다.  
  
 **\/kernel\-**  
 현재 프로젝트에 코드를 컴파일하여 커널 모드에서 실행 되는 코드에 관련된 c \+ \+ 언어 규칙을 사용하여 연결 합니다.  
  
## 설명  
 이 옵션을 제어하는 데 `#pragma`와 동일한 옵션은 없습니다.  
  
 지정 하는  **\/kernel**  옵션은 컴파일러와는 런타임이 불안정을 방지 하기 위해 충분 한 표현 능력 있다고는 커널 모드 c \+ \+ 링커 커널 모드에서 허용 되는 언어 기능을 조정 하 고 있는지 확인을 지시 합니다.  커널 모드에 방해가 되는 c \+ \+ 언어 기능의 사용을 금지 하 고 잠재적으로 파괴적 이지만 해제할 수 없는 c \+ \+ 언어 기능에 대 한 경고를 제공 하 여 수행 됩니다.  
  
 **\/kernel**  옵션 빌드 컴파일러와 링커 단계에 적용 하 고 프로젝트 수준에서 설정 됩니다.  전달 된  **\/kernel**  스위치는 결과 바이너리를 연결한 후에 로드 되어야 할 Windows 커널 컴파일러에 나타냅니다.  컴파일러는 커널 호환 되는 일부 c \+ \+ 언어 기능의 스펙트럼 범위를 좁힙니다.  
  
 다음 표에서 변경 된 컴파일러 동작에 때 **\/kernel** 를 지정 합니다.  
  
|동작 유형|**\/kernel** 동작|  
|-----------|---------------------|  
|C\+\+ 예외 처리|사용 안 함.  모든 인스턴스는 `throw` 및 `try` 컴파일러 오류를 생성 하는 키워드 \(예외 사양을 제외 하 고 `throw()`\).  **\/EH** 옵션은 호환 **\/kernel \/EH\-**를 제외하고 같이 쓸 수 있습니다.|  
|RTTI|사용 안 함.  모든 인스턴스는  `dynamic_cast`  및  `typeid`  키워드 하지 않으면 컴파일러 오류를 생성  `dynamic_cast`  정적으로 사용 됩니다.|  
|`new` 및 `delete`|명시적으로 정의 해야 하면  `new()`  또는  `delete()`  운영자입니다. 컴파일러와 런타임 모두 기본 정의 제공 합니다.|  
  
 사용자 지정 호출 규칙을의  [\/GS](../../build/reference/gs-buffer-security-check.md) 모든 최적화 및 빌드 옵션을 사용 하면 허용은  **\/kernel**  옵션.  인라인의 영향을 크게 받지  **\/kernel** , 컴파일러에 의해 적용 같은 의미입니다.   `__forceinline`  가 있는지 확인 하려는 경우는 인라인 한정자가 허용 해야 해당 경고,  [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 특정 알 수 있도록 사용  `__forceinline`  함수는 인라인 하지 않습니다.  
  
 **\/kernel** 스위치,이 미리 정의 라는 전처리기 매크로 `_KERNEL_MODE` 값과 **1**컴파일러에 전달된 경우를 확인할 수 있습니다.  이 조건에 따라 코드를 컴파일하려면 사용자 모드 또는 커널 모드 실행 환경 인지에 따라 사용할 수 있습니다.  예를 들어, 다음 코드에서는 지정 커널 모드 실행에 대 한 컴파일할 때 클래스 페이징할 수 없는 메모리 세그먼트에 있어야 합니다.  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
  
};  
  
```  
  
 일부 다음 조합을 대상 아키텍처 및 **\/arch** 옵션을 사용할 때 오류가 발생 **\/kernel** 합니다.  
  
-   **\/arch:{SSE&#124;SSE2&#124;AVX}**x 86에서 지원 되지 않습니다.  단지 **\/arch:IA32** 만 x86에서 **\/kernel** 사용할 수 있습니다.  
  
-   **\/arch:AVX** 는 **\/kernel** 를 x 64에서 지원 하지 않습니다.  
  
 **\/kernel** 또한 **\/kernel** 을 사용하여 구축합니다.  여기서 링커 동작에 미치는 영향을 보여줍니다.  
  
-   증분 링크를 사용할 수 없습니다.  **\/incremental** 명령줄에 추가 하는 경우 링커에서 이 오류를 보냅니다.  
  
     **LINK : fatal error LNK1295: '\/INCREMENTAL' not compatible with '\/KERNEL' specification; link without '\/INCREMENTAL'**  
  
-   링커는 각 개체 파일 \(또는 정적 라이브러리에서 포함 된 아카이브 멤버\) 여부를 그 수 컴파일된 사용하여 참조를 검사 하면 **\/kernel** 옵션이 있지만 하지 않았습니다.  이러한 조건을 만족 하는 모든 인스턴스, 링커 성공적으로 연결 하지만 다음 표에 표시 된 대로 경고를 발생할 수 있습니다.  
  
    ||**\/kernel** obj|**\/kernel\-** obj, MASM obj 또는 cvtresed|**\/kernel** 과 **\/kernel\-** 의 혼합 objs|  
    |-|----------------------|----------------------------------------------|---------------------------------------------|  
    |**\/kernel 링크**|예|예|예 경고 LNK4257와 함께|  
    |**link**|예|예|예|  
  
     **LNK4257 linking object not compiled with \/KERNEL ; image may not run**  
  
 **\/kernel** 옵션 및 **\/driver** 옵션 독립적으로 작동하고 다른 영향을 둘 다 미칩니다.  
  
### Visual Studio에서 \/kernel 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에서 `/kernel` 또는 `/kernel-`를 추가하세요.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)