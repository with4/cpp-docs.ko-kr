---
title: 다중 스레드 프로그램 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ece834bd6bf85daacbbaf50110e6e278da1ae099
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686934"
---
# <a name="multithread-programs"></a>다중 스레드 프로그램
스레드는 기본적으로 프로그램을 통해 실행 경로입니다. Win32 일정을 예약 하는 실행의 최소 단위 이기도 합니다. CPU 레지스터와 시스템 스케줄러의 실행 목록에 있는 항목의 상태는 스택, 스레드 구성 됩니다. 각 스레드는 프로세스의 모든 리소스를 공유합니다.  
  
 하나 이상의 스레드가 및 코드, 데이터 및 메모리에 있는 프로그램의 다른 리소스의 프로세스 구성 됩니다. 일반적인 프로그램 리소스가 열려 있는 파일, 세마포 및 동적으로 할당 된 메모리입니다. 시스템 스케줄러 스레드 중 하나 실행 컨트롤을 제공 하면 프로그램이 실행 합니다. 스케줄러는 스레드를 실행 해야 하며 실행 되는 시기를 결정 합니다. 우선 순위가 낮은 스레드가 우선 순위가 높은 스레드가 작업을 완료할 때 대기 해야 합니다. 스케줄러 다중 프로세서 컴퓨터에서 CPU 부하를 분산 하는 서로 다른 프로세서를 개별 스레드를 이동할 수 있습니다.  
  
 각 스레드는 프로세스에서 독립적으로 작동합니다. 으로 만들지 않으면 서로 보이지, 개별적으로 실행 스레드와 다른 스레드가 프로세스에서 인식 하지 않습니다. 그러나 공용 리소스를 공유 하는 스레드 세마포 또는 프로세스 간 통신의 기타 방법을 사용 하 여 작업을 조정 해야 합니다. 스레드를 동기화 하는 방법에 대 한 자세한 내용은 참조 [다중 스레드 Win32 프로그램 작성](../parallel/writing-a-multithreaded-win32-program.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)