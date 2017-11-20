---
title: ". 모델 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .MODEL
dev_langs: C++
helpviewer_keywords: .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d4ea26a75d37e264344aaacfa660e6d66dc8d5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="model"></a>.MODEL
프로그램 메모리 내 모델을 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memorymodel`  
 코드와 데이터 포인터의 크기를 결정 하는 필수 매개 변수입니다.  
  
 `langtype`  
 프로시저 및 공용 기호에 대 한 호출 및 명명 규칙을 설정 하는 선택적 매개 변수입니다.  
  
 `stackoption`  
 선택적 매개 변수입니다.  
  
 `stackoption`경우에 사용 되지 않는 `memorymodel` 은 `FLAT`합니다.  
  
 지정 `NEARSTACK` 스택 세그먼트를 단일 실제 세그먼트로 그룹화 (`DGROUP`) 데이터와 함께 합니다. 스택 세그먼트 레지스터 (`SS`)는 데이터 세그먼트 레지스터와 같은 주소를 보유할으로 간주 됩니다 (`DS`). `FARSTACK`포함 된 스택 그룹화 하지 않습니다 `DGROUP`39 `SS` 같지 않음 `DS`합니다.  
  
## <a name="remarks"></a>설명  
 .`MODEL` 사용 되지 않는 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
 다음 표에서 16 비트 및 32 비트 플랫폼을 대상으로 할 때 사용할 수 있는 각 매개 변수에 값을 나열 합니다.  
  
|매개 변수|32 비트 값|16 비트 값 (이전 16 비트 개발에 대 한 지원)|  
|---------------|--------------------|----------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|사용되지 않음|`NEARSTACK`, `FARSTACK`|  
  
## <a name="code"></a>코드  
 MASM 관련 샘플에서 컴파일러 샘플을 다운로드 [Visual c + + 샘플 및 Visual Studio 2010에 대 한 관련 문서](http://go.microsoft.com/fwlink/?LinkID=178749)합니다.  
  
 다음 예제에서는 `.MODEL` 지시문입니다.  
  
## <a name="example"></a>예제  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)   
 [Visual c + + 샘플 및 Visual Studio 2010에 대 한 관련된 문서](http://go.microsoft.com/fwlink/?LinkID=178749)