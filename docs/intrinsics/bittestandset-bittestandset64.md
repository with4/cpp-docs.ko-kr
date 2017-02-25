---
title: "_bittestandset, _bittestandset64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandset_cpp"
  - "_bittestandset64_cpp"
  - "_bittestandset64"
  - "_bittestandset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bittestandset 내장"
  - "_bittestandset64 내장"
  - "bts 명령"
ms.assetid: 6d6c8670-fea0-4c1c-9aad-2bb842715203
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _bittestandset, _bittestandset64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 주소 `a`의 비트 `b`를 검사하고 현재 값을 반환한 다음 비트를 1로 설정하는 명령을 생성합니다.  
  
## 구문  
  
```  
unsigned char _bittestandset(    long *a,    long b ); unsigned char _bittestandset64(    __int64 *a,    __int64 b );  
```  
  
#### 매개 변수  
 \[in, out\] `a`  
 검사할 메모리에 대한 포인터입니다.  
  
 \[in\] `b`  
 테스트할 비트 위치입니다.  
  
## 반환 값  
 지정한 위치에 있는 비트입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_bittestandset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
## 예제  
  
```  
// bittestandset.cpp  
// processor: x86, ARM, x64  
// This example uses several of the _bittest family of intrinsics  
// to implement a Flags class that allows bit level access to an  
// integer field.  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandset, _bittestandreset,\  
                  _bittestandcomplement, _bittest)  
  
class Flags  
{  
private:  
    long flags;  
    long* oldValues;  
  
public:  
    Flags() : flags(0)  
    {  
        oldValues = new long[32];  
    }  
  
    ~Flags()  
    {  
        delete oldValues;  
    }  
  
    void SetFlagBit(long nBit)  
    {  
        // We omit range checks on the argument  
        oldValues[nBit] = _bittestandset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
    }  
    void ClearFlagBit(long nBit)  
    {  
        oldValues[nBit] = _bittestandreset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
    }  
    unsigned char GetFlagBit(long nBit)  
    {  
        unsigned char result = _bittest(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
        return result;  
    }  
    void RestoreFlagBit(long nBit)  
    {  
        if (oldValues[nBit])  
            oldValues[nBit] = _bittestandset(&flags, nBit);  
        else  
            oldValues[nBit] = _bittestandreset(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);       
    }  
    unsigned char ToggleBit(long nBit)  
    {  
        unsigned char result = _bittestandcomplement(&flags, nBit);  
        printf_s("Flags: 0x%x\n", flags);  
        return result;  
    }  
};  
  
int main()  
{  
    Flags f;  
    f.SetFlagBit(1);  
    f.SetFlagBit(2);  
    f.SetFlagBit(3);  
    f.ClearFlagBit(3);  
    f.ToggleBit(1);  
    f.RestoreFlagBit(2);  
}  
```  
  
  **플래그: 0x2**  
**플래그: 0x6**  
**플래그: 0xe**  
**플래그: 0x6**  
**플래그: 0x4**  
**플래그: 0x0**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)