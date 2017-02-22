---
title: "_heapwalk | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapwalk"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "heapwalk"
  - "_heapwalk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_heapwalk 함수"
  - "디버깅[CRT], 힙 관련 문제"
  - "heapwalk 함수"
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _heapwalk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙이 통과하고 다음 항목에 관한 정보를 반환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### 매개 변수  
 `entryinfo`  
 힙 정보를 포함하는 버퍼입니다.  
  
## 반환 값  
 `_heapwalk` 는 Malloc.h에 정의된 다음 정수 매니페스트 상수 중 하나를 반환 합니다.  
  
 `_HEAPBADBEGIN`  
 초기 헤더 정보가 잘못 됬거나 없습니다.  
  
 `_HEAPBADNODE`  
 힙 손상 또는 잘못된 노드를 찾을 수 있습니다.  
  
 `_HEAPBADPTR`  
 `_HEAPINFO` 의 `_pentry` 필드 구조는 힙에 대한 유효한 포인터를 포함합니다. 또는 `entryinfo` 은 null 포인터입니다.  
  
 `_HEAPEND`  
 힙 끝에 성공적으로 도달 했습니다.  
  
 `_HEAPEMPTY`  
 힙은 초기화되지 않습니다.  
  
 `_HEAPOK`  
 지금까지 에러가 없다면 ; `entryinfo` 은 다음 힙 항목에 대한 정보를 업데이트합니다.  
  
 게다가, 오류가 발생 한 경우 `_heapwalk` 은 `errno` 를 `ENOSYS`설정합니다.  
  
## 설명  
 `_heapwalk` 함수는 프로그램에서 디버그 힙 관련 문제를 돕습니다.  함수는 호출당 하나의 항목을 탐색하는 힙을 보여줍니다. 그리고 다음 힙 항목에 관한 정보가 들어 있는 `_HEAPINFO` 의 형식 구조에서 포인터를 반환합니다.  Malloc.h에 정의된 `_HEAPINFO` 형식은 다음과 같은 요소를 포함합니다.  
  
 `int *_pentry`  
 힙 항목 포인터입니다.  
  
 `size_t _size`  
 힙 항목의 크기입니다.  
  
 `int _useflag`  
 노드가 사용 중인지 여부를 나타내는 플래그입니다.  
  
 `_HEAPOK` 를 반환하는 `_heapwalk` 호출은 `_size` 필드에서 항목 크기를 저장합니다. 그리고 `_useflag` 필드는 `_FREEENTRY` 또는 `_USEDENTRY` \(둘 다 Malloc.h에 정의 된 상수\)를 설정합니다.  힙에있는 첫번쨰 항목에 관한 정보를 얻기 위하여, `_heapwalk` 는 `_HEAPINFO` 구조를 통과합니다. `_pentry` 는 `NULL`을 멤버로 갖습니다.  운영 체제를 지원 하지 않는 경우, `_heapwalk`\(예: Windows 98\), 함수는 `_HEAPEND` 을 반환하고 `errno` 를 `ENOSYS` 설정합니다.  
  
 이 함수는 매개변수를 인증합니다.  만약 `entryinfo` 가 널 포인터라면, 잘못된 매개변수 처리기가 호출됩니다, 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)로 설명됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `_HEAPBADPTR` 을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_heapwalk`|\<malloc.h\>|\<\<errno.h\>\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
  **블록 00310650 의 크기 0100 사용**  
 **블록 00310758 의 크기 0800 사용**  
 **블록 00310F60 의 크기 0080 사용**  
 **블록 00310FF0 의 크기 0398 사용**  
 **블록 00311390 의 크기 000D 사용**  
 **블록 003113A8 의 크기 00B4 사용**  
 **블록 00311468 의 크기 0034 사용**  
 **블록 003114A8 의 크기 0039사용**  
**...**  
 **블록 00312228 의 크기 0010 사용**  
 **블록 00312240 의 크기1000 사용**  
 **블록 00313250 의 크기1DB0 사용**  
**확인\-힙 끝**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)