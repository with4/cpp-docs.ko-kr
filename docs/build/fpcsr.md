---
title: FpCsr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b7caebc99c4724c0e28b7812da8ef224184385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fpcsr"></a>FpCsr
레지스터 상태에도 x87 FPU 제어 단어입니다. 호출 규칙 비휘발성 되도록이 레지스터를 결정 합니다.  
  
 프로그램 실행을는 x87 FPU 제어 단어 레지스터의 시작 부분에 다음과 같은 표준 값으로 설정 됩니다.  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 FPCSR 내의 필드를 수정 하는 호출 수신자는 호출자에 반환 하기 전에 복원 해야 합니다. 또한가 이러한 필드를 수정 하는 호출자가 해야 복원할 표준 값으로 계약에 의해 호출 수신자는 수정 된 값이 필요 하지 않는 한 호출 수신자를 호출 하기 전에.  
  
 제어 플래그의 비-변동성에 대 한 규칙을 두 가지 예외가 있습니다.  
  
1.  비휘발성 FpCsr 수정 하려면 지정 된 함수의 문서화 된 목적은 함수 플래그 지정 합니다.  
  
2.  갖는 경우에 이러한 규칙 위반에 없는 이러한 규칙을 위반 하지 않은 예를 들어 전체 프로그램 분석을 통해 프로그램와 동일 하 게 작동/의미는 프로그램에서 결과 수정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)