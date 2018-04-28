---
title: ML 오류 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fbc2ae6388ad11a411850d03de421d2f6820fc03
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="ml-error-messages"></a>ML 오류 메시지
MASM 구성 요소에 의해 생성 된 오류 메시지는 세 가지 범주로 나뉩니다.  
  
-   **심각한 오류입니다.** 이러한 유틸리티의 일반적인 프로세스를 완료 하지 못하게 하는 심각한 문제를 나타냅니다.  
  
-   **치명적이 지 않은 오류가 발생 했습니다.** 유틸리티는 해당 프로세스를 완료할 수 있습니다. 그렇지 않으면 해당 결과를 원하는 어렵습니다.  
  
-   **경고입니다.** 이 메시지는 원하는 결과 얻지 못하도록 방지할 수 있는 조건을 나타냅니다.  
  
 모든 오류 메시지에는 다음 형식을 따릅니다.  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `Utility`  
 오류 메시지를 전송 하는 프로그램입니다.  
  
 *Filename*  
 오류 생성 조건을 포함 하는 파일입니다.  
  
 *Line*  
 오류 조건이 있는 대략적인 선입니다.  
  
 *Error_type*  
 심각한 오류, 오류 또는 경고 합니다.  
  
 *코드*  
 고유 5 또는 6 자리 오류 코드입니다.  
  
 `Message_text`  
 오류 조건의 짧고 일반 설명입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)