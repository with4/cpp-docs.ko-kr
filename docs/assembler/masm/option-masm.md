---
title: 옵션 (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057723"
---
# <a name="option-masm"></a>OPTION (MASM)
사용 하도록 설정 하 고는 어셈블러의 기능을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>설명  
 사용 가능한 옵션은 다음과 같습니다.  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**에뮬레이터**|  
|**NOEMULATOR**|**에필로그**|**EXPR16**|**EXPR32**|  
|**언어**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**프롤로그**|**읽기 전용**|**NOREADONLY**|  
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**합니다.|  
  
 언어에 대 한 구문은 **옵션 언어: * * * x*여기서 *x* C, SYSCALL, STDCALL, PASCAL, 포트란 또는 BASIC 중 하나입니다.  SYSCALL "," PASCAL "," FORTRAN, "및" BASIC 지원 되지 않습니다와 함께 사용할 [합니다. 모델](../../assembler/masm/dot-model.md) 평면입니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)