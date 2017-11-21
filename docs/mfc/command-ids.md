---
title: "명령 Id | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95b531d12afc524e27bf36fc5a44d5f555fc9f91
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="command-ids"></a>명령 ID
명령 대 한 자세한 내용은 해당 명령 ID만로 (인코딩된는 **WM_COMMAND** 메시지). 이 ID는 명령을 생성 하는 사용자 인터페이스 개체에 할당 됩니다. 일반적으로 Id에 할당 된 사용자 인터페이스 개체의 기능에 대 한 이름이 지정 됩니다.  
  
 예를 들어 편집 메뉴에서 모두 지우기 항목 할당 될 수 있습니다는 ID와 같은 **ID_EDIT_CLEAR_ALL**합니다. 클래스 라이브러리는 명령 프레임 워크에서와 같은 자체를 처리 하는 데 일부 Id **ID_EDIT_CLEAR_ALL** 또는 `ID_FILE_OPEN`합니다. 다른 명령 Id를 직접 만듭니다 됩니다.  
  
 표시 된 것 처럼 클래스 라이브러리를 수행 하는 것이 좋습니다의 명명 규칙은 자신의 메뉴는 Visual c + +에서 메뉴 편집기를 만들면 `ID_FILE_OPEN`합니다. [표준 명령](../mfc/standard-commands.md) 클래스 라이브러리에 정의 된 표준 명령에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 개체 및 명령 ID](../mfc/user-interface-objects-and-command-ids.md)

