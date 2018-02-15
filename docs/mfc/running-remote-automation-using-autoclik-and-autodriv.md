---
title: "AUTOCLIK 및 AUTODRIV를 사용 하 여 원격 자동화 실행 | Microsoft Docs"
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
- AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 791655047eaf07732e1e006e8cc3ea8e7dec4727
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>AUTOCLIK 및 AUTODRIV를 사용하여 원격 자동화 실행
AUTOCLIK 원격 자동화에 대 한 자세한 내용을 보려면를 기반으로 사용할 수 있는 간단한 자동화 서버 샘플 응용 프로그램이 있습니다. AUTODRIV는 AUTOCLIK를 구동 하는 간단한 자동화 클라이언트 응용 프로그램입니다. 원격 자동화를 보여 주기 위해 사용할 수 있습니다.  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>AUTOCLIK를 설치 하려면 EXE를 설치 하 고 원격 자동화를 사용 하 여 드라이브  
  
1.  설치는 [AUTOCLIK](../visual-cpp-samples.md) 샘플 응용 프로그램 개발 컴퓨터에 있습니다.  
  
2.  AUTOCLIK를 빌드하십시오. EXE 합니다.  
  
3.  AUTOCLIK를 실행 합니다. 독립 실행형 EXE 방식으로 한 후 종료 합니다. 이 자동화 서버도 등록 됩니다.  
  
4.  AUTOCLIK를 복사 합니다. 원격 컴퓨터에 대 한 EXE를 실행 한 후 종료 합니다.  
  
5.  AUTODRIV를 실행 합니다. EXE 로컬 컴퓨터 및 실행 하는 AUTOCLIK 시작 됨을 확인 합니다. EXE 합니다. AUTODRIV에 대 한 자세한 내용을 보려면 합니다. EXE가 참조 [AUTOCLIK](../visual-cpp-samples.md)합니다.  
  
6.  원격 컴퓨터에서 AUTMGR32를 시작 합니다. EXE (자동화 관리자)입니다.  
  
7.  원격 컴퓨터에서 RACMGR32를 시작 합니다. EXE (원격 자동화 연결 관리자)입니다.  
  
8.  원격 자동화 연결 관리자의 선택에서 AutoClik.Document는 **OLE 클래스** 목록입니다.  
  
9. 시스템 보안 정책에서 선택 된 **클라이언트 액세스** AutoClik.Document에 대 한 클라이언트 액세스를 부여할 탭 합니다.  
  
10. 로컬 컴퓨터에서 RACMGR32를 시작 합니다. EXE 및에서 선택 AutoClik.Document는 **OLE 클래스** 목록입니다.  
  
11. **서버 연결** 탭에서 적절 한 네트워크 프로토콜 및 원격 컴퓨터의 네트워크 주소를 선택 합니다.  
  
12. 선택 된 AutoClik.Document 상태와는 **OLE 클래스** 목록 상자를 선택는 **원격** 명령을 `Register` 메뉴.  
  
13. 로컬 컴퓨터에서 AUTODRIV를 실행 합니다. EXE 또는 동등한 AUTOCLIK 합니다. MAK Visual Basic 프로젝트는 MFC 아닌 Visual Basic의 경우 하려는 경우 클라이언트입니다.  
  
 원격 컴퓨터에서 이제 해야 AUTOCLIK 실행 로컬 클라이언트에서 시작 된 명령을 볼 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [원격 자동화](../mfc/remote-automation.md)

