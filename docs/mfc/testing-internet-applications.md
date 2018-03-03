---
title: "인터넷 응용 프로그램 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cc214eb98b8aa9e927fd471ba313e4cade426a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="testing-internet-applications"></a>인터넷 응용 프로그램 테스트
웹 서버에서 실행 중인 응용 프로그램에 대 한 특히 인터넷에 몇 가지 고유한 테스트 방법이 있습니다. 초기 테스트 아마도 수행 됩니다 테스트 서버에 연결 하는 단일 사용자 클라이언트를 사용 하 여 합니다. 이 코드를 디버깅에 유용 합니다.  
  
 실제 조건에서 테스트 하려면 또한: 저속 직렬 회선 뿐 아니라 고속 연결을 통해 연결의 여러 클라이언트를 모뎀 연결을 포함 합니다. 실제 환경에서 테스트 하기 어려울 수는 있지만 가치가 시간 디자인 가능한 시나리오를 소비 하 고 실행 하는 합니다. 가능 하면 do 용량 및 스트레스 테스트 도구를 사용 하려는 수도 있습니다. 일부 버그 타이밍 버그와 같은 클래스는 찾으려면를 재현 하기 어렵습니다.  
  
 인터넷 프로그래밍의 과제 중 하나는 표시입니다. 사이트에 대 한 많은 액세스 서버의 속도가 저하 될 수 있습니다. 정상적 저하 하려면 서버를 사용 하는 것이 좋습니다. 손상 되지 않도록 할 수는 사용자의 컴퓨터에 응용 프로그램 (예: 레지스트리를 쓰는 동안 또는 클라이언트에 쿠키를 쓰는 동안 데이터의 손상) 못하면 하려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

