---
title: 다중 스레드 프로그램으로 문제 영역 방지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af4c1ca6a86b2cff457aee12e8337103ce7f42d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>다중 스레드 프로그램으로 문제 영역 방지
만들기, 링크 또는 다중 스레드 C 프로그램을 실행할 때 발생할 수 있는 몇 가지 문제가 있습니다. 일반적인 문제 중 일부는 다음 표에 설명 되어 있습니다. (MFC의 관점에서 비슷한 논의 알려면 [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md).)  
  
|문제점|가능한 원인|  
|-------------|--------------------|  
|얻게 프로그램 보호 위반이 발생 한 것을 보여 주는 메시지 상자.|보호 위반이 발생 하는 많은 Win32 프로그래밍 오류. 보호 위반의 일반적인 원인에는 null 포인터에 대 한 데이터의 간접 할당입니다. 이 식의 결과에 속하지 않는 메모리에 액세스 하려고 하는 프로그램에서 때문에 보호 위반이 발생 합니다.<br /><br /> 쉽게 보호 위반의 원인을 파악 하는 방법을를 디버깅 정보를 사용 하 여 프로그램을 컴파일하고 다음 Visual c + + 환경에서 디버거를 통해 실행 됩니다. 보호 오류가 발생할 때 Windows 컨트롤 디버거 전송 되 고 문제가 발생 한 줄에 커서가 놓입니다.|  
|프로그램 다양 한 컴파일 및 링크 오류를 생성합니다.|가장 높은 값 중 하나에 컴파일러의 경고 수준을 설정 하 고 경고 메시지에 주의 하 여 많은 잠재적 문제를 제거할 수 있습니다. 수준 3 또는 수준 4 경고 수준 옵션을 사용 하 여 의도 하지 않은 데이터 변환, 누락 된 함수 프로토타입 및 비-ANSI 기능의 사용을 검색할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)