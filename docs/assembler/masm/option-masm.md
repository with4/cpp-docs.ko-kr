---
title: "OPTION (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# OPTION (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

수 있으며 어셈블러의 기능을 사용 하지 않도록 설정 합니다.  
  
## 구문  
  
```  
  
OPTION   
optionlist  
  
```  
  
## 설명  
 사용할 수 있는 옵션은 다음과 같습니다.  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**에뮬레이터**|  
|**NOEMULATOR**|**에필로그**|**EXPR16**|**EXPR32**|  
|**언어**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**오프셋**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**\-프로세서**|**프롤로그**|**READONLY**|**NOREADONLY**|  
|**범위 지정**|**NOSCOPED**|**세그먼트**|**SETIF2**.|  
  
 언어의 구문입니다  **옵션 언어:***x*, 어디  *x* C, 시스템 호출, STDCALL, 파스칼, 포트란, 또는 기본 중 하나입니다.  시스템 호출, 파스칼, 포트란 및 기본 지원 하지 않습니다와 함께 사용 되는 [.MODEL](../../assembler/masm/dot-model.md) 플랫.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)