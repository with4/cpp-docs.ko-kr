---
title: "원격 자동화가 필요한 경우 | Microsoft 문서"
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
- Remote Automation, DCOM
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad6eef0bbaad7860e7f4310ce283efe18c668eb
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="where-does-remote-automation-fit-in"></a>원격 자동화가 필요한 경우
DCOM은 1996 년에 릴리스된 되며 32 비트 및 64 비트 플랫폼에만 사용할 수 있습니다. Microsoft Visual Basic 팀 자동화를 사용 하 여 해당 구성 요소가 통신할 수 있도록 Visual Basic 항상 문제가 했습니다. Visual Basic 4.0 Enterprise Edition 개발 팀에서 자동화에 대 한 원격 구성 요소는 자체 집합 했기 하기로 심각 하 게 분산된 버전 부족 엔터프라이즈 환경에서이 기능의 사용 제한 부분 있었습니다. 명확 하 게 주요 목표는 이었습니다 결과와 호환 되는 것을 사용할 수 있게 하는 경우 DCOM으로 대체할 수 있습니다. 16 비트 및 32 비트 Windows 플랫폼에 대 한 자동화 RA (원격)를 구현 하려면 다음 진행 합니다.  
  
 원격 자동화는 특정 언어에 연결 되지 않은 하지만 Visual Basic 4.0 에서만 발송 된 Visual c + + 4.2 Enterprise Edition을 해제할 때까지 합니다. 원격 자동화 DCOM에서 전체적으로 포함 됩니다. 알아야 합니다. 원격 자동화 하는 대신 응용 프로그램에서 DCOM을 사용 하 여, 있는 경우이 수행 해야 있습니다. 그럼에도 불구 하 고 원격 자동화가 더 적합 한 시나리오가 있습니다.  
  
-   16 비트 클라이언트가 있는 경우.  
  
-   조직에 롤백되지 DCOM 사용이 가능한 버전의 Windows NT 또는 Windows 95 아웃 아직 하는 경우.  
  
-   기존 응용 프로그램 도구 모음을 업그레이드 하는 경우 원격 자동화를 사용 하는 하나 이상의 Visual Basic 구성 요소 대신 사용 하 여 c + + 구성 요소에 합니다.  
  
 원격 자동화 및 DCOM을 통해 자동화를 사용 하도록 만든 사용 하 여 만든 프로그램 사이 차이가 있을 필요는 없으며 하 고 구성 유틸리티 확인 원격 자동화과 DCOM 간의 작업을 전환 하는 매우 간단 합니다. 따라서는 인프라스트럭처가 준비 되 면 DCOM 원격 자동화에서 응용 프로그램 업그레이드 어렵지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화의 기능은 무엇입니까](what-does-remote-automation-provide-q.md)   
 [DCOM의 역사](../mfc/history-of-dcom.md)
