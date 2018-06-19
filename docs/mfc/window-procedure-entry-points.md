---
title: 창 프로시저 진입점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1095061cce8ff8f189984aca99a06eb741a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382075"
---
# <a name="window-procedure-entry-points"></a>창 프로시저 진입점
MFC 창 프로시저를 모듈 정적 특수 창 프로시저 구현으로 링크를 보호 합니다. 한 링크를 모듈 MFC와 함께 연결 될 때 자동으로 발생 합니다. 이 창 프로시저를 사용 하 여는 `AFX_MANAGE_STATE` 매크로를 호출 하는 다음 유효한 모듈 상태를 올바로 설정 **AfxWndProc**, 차례로에 위임 하는 `WindowProc` 적절 한 멤버 함수 `CWnd`-파생 된 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)

