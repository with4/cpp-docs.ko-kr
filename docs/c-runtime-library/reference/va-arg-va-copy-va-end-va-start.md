---
title: "va_arg, va_copy, va_end, va_start | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "va_arg"
  - "va_end"
  - "va_copy"
  - "va_start"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "va_arg"
  - "va_start"
  - "va_list"
  - "va_alist"
  - "va_dcl"
  - "va_copy"
  - "va_end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "에 액세스 하는 가변 인수 목록"
  - "va_start 매크로"
  - "va_arg 매크로"
  - "va_end 매크로"
  - "인수 [c + +] 인수 목록"
  - "va_list 매크로"
  - "va_dcl 매크로"
  - "va_alist 매크로"
  - "va_copy 매크로"
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# va_arg, va_copy, va_end, va_start
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액세스 가변 인수 목록입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      type va_arg(  
   va_list arg_ptr,  
   type   
);void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 인수를 검색할 형식입니다.  
  
 `arg_ptr`  
 인수 목록에 대 한 포인터입니다.  
  
 `dest`  
 초기화는 인수 목록에 대 한 포인터 `src`  
  
 `src`  
 초기화를 복사 하는 인수 목록에 대 한 포인터 `dest`합니다.  
  
 `prev_param`  
 첫 번째 선택적 인수 앞에 오는 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 `va_arg` 현재 인수를 반환합니다. `va_copy`, `va_start` 및 `va_end` 값을 반환 하지 않습니다.  
  
## <a name="remarks"></a>주의  
  `va_arg`, `va_copy`, `va_end`, 및 `va_start` 매크로 함수는 가변 인수 수를 사용 하는 경우 함수에 대 한 인수를 액세스 하는 이식 가능한 방법을 제공 합니다. 매크로의 두 버전: STDARG에 정의 된 매크로입니다. H 준수 ISO C99 표준입니다. VARARGS에 정의 된 매크로입니다. H 사용 되지 않습니다. 하지만 ANSI c 89에서 표준 전에 작성 된 코드와 이전 버전과 호환성을 위해 유지 됩니다.  
  
 이러한 매크로 함수는 고정된 개수의 다양 한 선택적 인수 뒤 필수 인수를 수행 하는지 가정 합니다. 필수 인수가 함수에는 일반 매개 변수로 선언 되 고 매개 변수 이름을 통해 액세스할 수 있습니다. 선택적 인수는 STDARG의 매크로 통해 액세스 됩니다. H (또는 VARARGS 합니다. H는 ANSI c 89에서 표준 전에 작성 된 코드에 대 한) 인수 목록의 첫 번째 선택적 인수에 대 한 포인터를 설정 하는 목록에서 인수를 검색 하 고 인수 처리가 완료 되 면 마우스 포인터를 다시 설정 합니다.  
  
 C 표준 매크로 STDARG에 정의 합니다. H, 다음과 같이 사용 됩니다.  
  
-   `va_start` 설정 `arg_ptr` 함수에 전달 되는 인수 목록에서 첫 번째 선택적 인수를 합니다. 인수 `arg_ptr` 있어야는 `va_list` 유형입니다. 인수 `prev_param` 인수 목록에서 바로 앞에 오는 첫 번째 선택적 인수는 필수 매개 변수 이름입니다. 경우 `prev_param` 매크로 동작은 정의 되지 않았습니다 레지스터 저장소 클래스를 사용 하 여 선언 됩니다. `va_start` 이전에 사용 될 `va_arg` 처음으로 사용 됩니다.  
  
-   `va_arg` 값을 검색 `type` 하 여 지정 된 위치에서 `arg_ptr`, 씩 증가 `arg_ptr` 의 크기를 사용 하 여 목록에서 다음 인수를 가리키도록 `type` 다음 인수 시작 위치를 결정 합니다. `va_arg` 가능 함수에 인수를 검색 하려면 목록에서 원하는 횟수 만큼을 사용 합니다.  
  
-   `va_copy` 현재 상태에서 인수 목록의 복사본을 만듭니다.  `src` 매개 변수가 이미 초기화 해야 `va_start`; 것이로 업데이트 된 `va_arg` 를 호출 하지만 해야 하지 재설정 되었을와 `va_end`합니다. 검색 된 다음 인수 `va_arg` 에서 `dest` 에서 검색 된 다음 인수 동일 `src`합니다.  
  
-   모든 인수를 검색 한 후 `va_end` 에 대 한 포인터를 다시 설정 **NULL**합니다. `va_end` 각 인수 목록을 사용 하 여 초기화를 호출 해야 `va_start` 또는 `va_copy` 함수가 반환 되기 전에 합니다.  
  
> [!NOTE]
>  VARARGS에 매크로입니다. H는 사용 되지 않으며는 이전 버전과 ANSI c 89에서 표준 전에 작성 된 코드와의 호환성에 대해서만 유지 합니다. 다른 모든 경우에 STDARGS에 매크로 사용 합니다. 8.  
  
 사용 하 여 컴파일할 때 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md), 이러한 매크로 사용 하는 프로그램 네이티브 및 공용 언어 런타임 (CLR) 형식 시스템 간의 차이 때문에 예기치 않은 결과 생성할 수 있습니다. 이 프로그램을 고려해 야 합니다.  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 다음에 유의 `testit` 어느 쪽이 든의 두 번째 매개 변수는 `int` 또는 `char*`합니다. 전달 되는 인수는 0xffffffff (한 `unsigned int`, 이 아니라는 `int`) 및 `NULL` (실제로 `int`, 이 아니라는 `char*`). 네이티브 코드에 대 한 프로그램 컴파일되면이 출력을 생성 합니다.  
  
```Output  
-1  
  
(null)  
```  
  
 그러나 프로그램을 사용 하 여 컴파일할 때에 **/clr: pure**, 형식 불일치 예외를 생성 하도록 할 합니다. 솔루션 명시적 캐스트를 사용 하는 것입니다.  
  
```  
int main()  
{  
   testit( 0, (int)0xFFFFFFFF ); // cast unsigned to int  
   testit( 1, (char*)NULL );     // cast int to char*  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<. h > 및 \< g. h >  
  
 **사용 되지 않는 머리글:** \< varargs.h >  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의는 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>출력  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 [System::ParamArrayAttribute 클래스](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [인수 액세스](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)