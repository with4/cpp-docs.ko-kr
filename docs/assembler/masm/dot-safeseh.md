---
title: . SAFESEH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69212e7a3542a6b6ac88ccbe2ecbbf8894862e65
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="safeseh"></a>.SAFESEH
구조적된 예외 처리기로 함수를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>설명  
 *식별자* 로컬로 정의 대 한 ID 여야 합니다. [PROC](../../assembler/masm/proc.md) 또는 [EXTRN](../../assembler/masm/extrn.md) 프로시저 A [레이블](../../assembler/masm/label-masm.md) 허용 되지 않습니다. 합니다. SAFESEH 지시문에 필요한는 [/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe 명령줄 옵션입니다.  
  
 구조적된 예외 처리기에 대 한 자세한 내용은 참조 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)합니다.  
  
 예를 들어 안전한 예외 처리기를 등록 하려면 새 MASM 파일 (다음과 같은) 조합 하 여 /safeseh를 만들고 연결 된 개체에 추가 합니다.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)