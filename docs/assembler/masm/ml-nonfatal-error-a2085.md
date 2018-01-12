---
title: "ML 심각 하지 않은 오류 A2085 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f987b775c13b0e477fd5c1d215d556069535a0fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2085"></a>ML 심각하지 않은 오류 A2085
**명령 또는 레지스터 현재 CPU 모드에서 허용 되지 않습니다**  
  
 명령, 레지스터 또는 현재 프로세서 모드에 대 한 잘못 된 키워드를 사용 하려고 했습니다.  
  
 예를 들어 32 비트 레지스터 필요 [.386](../../assembler/masm/dot-386.md) 이상. CR0 필요한 특권된 모드와 같은 제어 레지스터 [.386P](../../assembler/masm/dot-386p.md) 이상. 이 오류에 대 한도 생성 됩니다는 **NEAR32**, **FAR32**, 및 **플랫** 키워드를 요구 합니다. **386** 이상.  
  
## <a name="see-also"></a>참고 항목  
 [ML 오류 메시지](../../assembler/masm/ml-error-messages.md)