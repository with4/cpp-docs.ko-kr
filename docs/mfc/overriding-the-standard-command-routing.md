---
title: 표준 명령 라우팅 재정의 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58156f6d1c361c24dc6cf04a9208157d614f91a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929012"
---
# <a name="overriding-the-standard-command-routing"></a>표준 명령 라우팅 재정의
드문 경우 이지만 라우팅 표준 프레임 워크의 몇 가지 변형 구현 해야 하는 경우 재정의할 수 있습니다. 재정의 하 여 하나 이상의 클래스 경로 변경 하는 개념은 `OnCmdMsg` 해당 클래스에 있습니다. 다음과 같이  
  
-   에 기본이 아닌 개체를 전달 하는 순서를 무시 하는 클래스입니다.  
  
-   명령 대상 또는 새 기본이 아닌 개체에 명령을 다시 전달할 수 있습니다.  
  
 라우팅에 몇 가지 새 개체를 삽입 하면 해당 클래스는 명령 대상 클래스 여야 합니다. 재정의 버전에서 `OnCmdMsg`, 재정의 하는 버전을 호출 해야 합니다. 참조는 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) 클래스의 멤버 함수 `CCmdTarget` 에 *MFC 참조* 와 같은 클래스에 버전 `CView` 및 `CDocument` 예제에 대 한 제공 된 소스 코드에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

