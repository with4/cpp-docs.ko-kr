---
title: "원격 자동화 설치 | Microsoft Docs"
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
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-installation"></a>원격 자동화 설치
원격 자동화 비교적 적은 구성 요소에 있습니다.  
  
-   원격 자동화 클라이언트 프록시를 AUTPRX32입니다. DLL입니다.  
  
-   원격 자동화 서버 쪽 구성 요소 자동화 관리자 AUTMGR32 합니다. EXE 합니다.  
  
-   RAC 관리자 RACMGR32입니다. EXE는 일치 하는 RACREG32 합니다. DLL입니다.  
  
 이 중 RAC 관리자는 Visual Basic로 작성 하 고 Visual Basic 런타임 지원 하므로 필요 합니다. 이러한 오류 코드 및 기타 원격 자동화 파일은 Visual c + + Enterprise Edition을 설치할 때 설치 프로그램에서 설치 됩니다.  
  
 Visual c + + 버전에서 Enterprise Edition이 설치 되지, 확인 하는 컴퓨터로 원격 자동화 구성 요소를 복사 하는 경우 해당 REGSRV32 합니다. EXE는 컴퓨터의 경로 및 RACREG32 등록할 수 있습니다. 다음 명령줄을 사용 하 여 DLL:  
  
 REGSRVR32 RACREG32 합니다. DLL  
  
> [!NOTE]
>  RAC 관리자의 Visual c + + 5.0 이전 버전 GUAGE32 필요합니다. OCX 및 TABCTL32 합니다. OCX 합니다. 이러한 버전의 RAC 관리자 함께 제공 되는 Visual c + + Enterprise edition 버전 5.0 이상 필요 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [자동화 관리자](../mfc/automation-manager-mfc.md)  
  
 [원격 자동화 연결 관리자](../mfc/remote-automation-connection-manager.md)  
  
 [원격 자동화 사용자 구성 요소](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화](../mfc/remote-automation.md)

