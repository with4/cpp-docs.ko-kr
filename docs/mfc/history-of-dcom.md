---
title: "DCOM의 역사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Remote Automation, DCOM
- DCOM, about DCOM
- DCOM
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9e5607fd240c7a97691189b8a3afa5e7c0171e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="history-of-dcom"></a>DCOM의 역사
자동화 초기 1993에서 처음 도입을 동일한 컴퓨터에서 실행 중인 응용 프로그램 사이만 사용할 수 있었습니다. 그러나 OLE를, COM (또는 구성 요소 개체 모델)의 나머지 부분과 동일한 기본 토대를 공유 하기 때문에 항상 원래 원격 기능을 포함 하도록 COM 자체를 업데이트할 때 "원격" 될 것을 합니다. 기존 코드를 거의 또는 전혀 변경 순수한 로컬 작업에서 분산된 작업으로 전환 해야 하는 계획도 되었습니다.  
  
 어떤 "원격" 의미 로컬 COM 인터페이스의 소비자 상주 하는 결정 되므로 해당 인터페이스의 공급자와 동일한 컴퓨터에 실행 합니다. 예를 들어 Microsoft Visual Basic 데스크톱 컴퓨터에 Microsoft Excel의 복사본을 제어할 수 있지만 다른 컴퓨터에 Excel의 실행 파일로 전송으로 수 없었습니다. 분산된 COM 개발으로 인터페이스의 소비자가 더 이상 인터페이스 공급자 실행 하는 것과 동일한 컴퓨터에 상주 합니다.  
  
 COM이 되는 네트워크를 통해 사용할 수 높일 면 다음 모든 인터페이스는 로컬 실행 모델에 연결 되지 했습니다 (일부 인터페이스 로컬 컴퓨터 기능에 대 한 내재 된 의존성, 등에 그리기 인 인터페이스 메서드에 사용할으로 장치 컨텍스트 핸들 매개 변수)를 배포 하는 기능이 것입니다. 인터페이스 소비자 하 게 만드는; 지정 된 인터페이스에 대 한 요청 해당 인터페이스는 다른 컴퓨터에서 실행 하는 개체 (또는 실행)의 인스턴스에 의해 제공 될 수 있습니다. COM 내부 배포 메커니즘 소비자는 방식으로 공급자에 연결 하는 소비자가 한 메서드 호출 부분에 표시 될 공급자 끝 실행은 위치입니다. 모든 반환 값은 다음 소비자에 게 보낼 수 있습니다. 에 모든 용도 배포 하는 작업은 소비자 및 공급자를 모두에 투명 합니다.  
  
 매우 다양 COM 존재 이제 않습니다. DCOM ("분산된 COM")을 포함 하 여 Windows 2000 및 Windows NT 버전 4.0부터 버전와 함께 제공 되었습니다. 런타임에 1996부터 것 에서도 사용할 수 있었던 Windows 9x 용 x. 두 경우 모두, DCOM 로컬 및 원격 COM 기능을 제공 하는 몇 가지 유틸리티와 대체 및 추가 Dll의 집합을 구성 합니다. 따라서 이제는 내재 된의 일부인 Win32 기반 플랫폼에서 하 고 사용 가능 하 게 다른 플랫폼에서 다른 조직에서 시간이 지남에 따라 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [원격 자동화가 필요한 경우 있습니까](where-does-remote-automation-fit-in-q.md)  
  
 [원격 자동화의 기능은 무엇입니까](what-does-remote-automation-provide-q.md)  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화](../mfc/remote-automation.md)
