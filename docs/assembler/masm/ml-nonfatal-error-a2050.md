---
title: "ML 심각 하지 않은 오류 A2050 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2050
dev_langs: C++
helpviewer_keywords: A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a51a90f294afd0347057efb04ab37ce790532ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2050"></a>ML 심각하지 않은 오류 A2050
**real 또는 BCD 번호를 사용할 수 없습니다**  
  
 부동 소수점 (실수) 또는 binary coded decimal (BCD) 상수 이외의 사용 데이터 이니셜라이저로 합니다.  
  
 다음 중 하나가 발생 했습니다.  
  
-   숫자는 실수 또는 BCD 식에 사용 되었습니다.  
  
-   숫자는 실수는 지시문을 이외의 초기화에 사용 된 [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), 또는 [TBYTE](../../assembler/masm/tbyte.md)합니다.  
  
-   BCD 지시문을 이외의 초기화에 사용 된 `TBYTE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ML 오류 메시지](../../assembler/masm/ml-error-messages.md)