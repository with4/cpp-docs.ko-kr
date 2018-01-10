---
title: "옵션 (MASM) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**오프셋**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**프롤로그**|**읽기 전용**|**NOREADONLY**|  
|**범위 지정**|**NOSCOPED**|**SEGMENT**|**SETIF2**합니다.|  
  
 언어에 대 한 구문은 **옵션 언어:***x*여기서 *x* C, SYSCALL, STDCALL, PASCAL, 포트란 또는 BASIC 중 하나입니다.  SYSCALL "," PASCAL "," FORTRAN, "및" BASIC 지원 되지 않습니다와 함께 사용할 [합니다. 모델](../../assembler/masm/dot-model.md) 평면입니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)