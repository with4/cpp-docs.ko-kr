---
title: . FPO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 61d9209b5cf817d89e9e017626222a9cc73e209e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fpo"></a>.FPO
합니다. FPO 지시문 섹션 이나.debug$ F 세그먼트에 디버그 레코드를 내보낼을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cdwLocals`  
 지역 변수는 부호 없는 32 비트 값의 수입니다.  
  
 `cdwParams`  
 DWORD, 부호 없는 16 비트 값의에서 매개 변수 크기입니다.  
  
 *cbProlog*  
 함수 프롤로그 코드는 부호 없는 8 비트 값의 바이트 수입니다.  
  
 `cbRegs`  
 저장 된 레지스터 번호입니다.  
  
 `fUseBP`  
 EBP 레지스터 할당 되었는지 여부를 나타냅니다. 0 또는 1입니다.  
  
 *cbFrame*  
 프레임 유형을 나타냅니다.  참조 [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)