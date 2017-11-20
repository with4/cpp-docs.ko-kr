---
title: "대화 상자 데이터 유효성 검사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 58fbff4a5192d15a60cf3340ce762574947fb249
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-data-validation"></a>대화 상자 데이터 유효성 검사
예제에 나와 있는 것 처럼 DDV 함수를 호출 하 여 데이터 교환 외에도 유효성 검사를 지정할 수 있습니다 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)합니다. `DDV_MaxChars` 예제에서 호출의 텍스트 상자 컨트롤에 입력 한 문자열이 20 자 보다 긴 아닌지 유효성을 검사 합니다. 일반적으로 DDV 함수는 유효성 검사가 실패 하 고 사용자 데이터를 다시 입력할 수 있도록 문제가 되는 컨트롤에 포커스를 둡니다 메시지 상자를 사용 하 여 경고 합니다. 지정된 된 컨트롤에 대 한 DDV 함수에서 동일한 컨트롤에 대 한 DDX 함수 직후 호출 되어야 합니다.  
  
 또한 사용자 고유의 사용자 지정 DDX 및 DDV 루틴을 정의할 수 있습니다. 이 및 DDX 및 DDV의 다른 측면에 대 한 내용은 참조 하십시오. [MFC 기술 참고 26](../mfc/tn026-ddx-and-ddv-routines.md)합니다.  
  
 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) DDV 데이터 맵에서 대 한 호출 수 및 모든 DDX는 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)

