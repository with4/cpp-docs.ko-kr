---
title: __debugbreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e9aa50ee6cf450276dce70bfa38162a2f6392ed
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="debugbreak"></a>__debugbreak
**Microsoft 전용**  
  
 코드에서 중단점이 발생하며 사용자에게 디버거를 실행하라는 메시지가 표시됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __debugbreak();  
```  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|Header|  
|---------------|------------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
  
## <a name="remarks"></a>설명  
 `__debugbreak` 컴파일러 내장 마찬가지로 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), 중단점 발생 하는 휴대용 Win32 방법이 있습니다.  
  
> [!NOTE]
>  로 컴파일할 때 **/clr**를 포함 하는 함수 `__debugbreak` MSIL로 컴파일할 수 있습니다. `asm int 3`은 함수를 네이티브로 컴파일하도록 합니다. 자세한 내용은 참조 [__asm](../assembler/inline/asm.md)합니다.  
  
 예:  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 위의 예는 아래 예와 유사합니다.  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 x86 컴퓨터의 경우  
  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [키워드](../cpp/keywords-cpp.md)