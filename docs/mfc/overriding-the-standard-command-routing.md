---
title: "표준 명령 라우팅 재정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a8f926a2aa9ed48dac24f75850876bbd1e04ef4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-the-standard-command-routing"></a>표준 명령 라우팅 재정의
드문 경우 이지만 라우팅 표준 프레임 워크의 몇 가지 변형 구현 해야 하는 경우 재정의할 수 있습니다. 재정의 하 여 하나 이상의 클래스 경로 변경 하는 개념은 `OnCmdMsg` 해당 클래스에 있습니다. 다음과 같이  
  
-   에 기본이 아닌 개체를 전달 하는 순서를 무시 하는 클래스입니다.  
  
-   명령 대상 또는 새 기본이 아닌 개체에 명령을 다시 전달할 수 있습니다.  
  
 라우팅에 몇 가지 새 개체를 삽입 하면 해당 클래스는 명령 대상 클래스 여야 합니다. 재정의 버전에서 `OnCmdMsg`, 재정의 하는 버전을 호출 해야 합니다. 참조는 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) 클래스의 멤버 함수 `CCmdTarget` 에 *MFC 참조* 내용과 같은 클래스 버전 `CView` 및 **CDocument** 에 예제에 대 한 소스 코드를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)

