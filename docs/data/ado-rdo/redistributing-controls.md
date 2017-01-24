---
title: "컨트롤 재배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 재배포"
  - "재배포 가능한 컨트롤"
ms.assetid: 32d03b95-d328-4f10-ad9b-f3ebbe03339d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컨트롤 재배포
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ .NET은 응용 프로그램에서 사용할 수 있는 ActiveX 컨트롤을 제공합니다. 그런 다음 응용 프로그램과 함께 컨트롤을 재배포할 수 있습니다.**ActiveX 컨트롤 삽입** 대화 상자에서 컨트롤을 강조 표시하면 해당 .ocx 또는 .dll 파일이 표시됩니다.  
  
 재배포 가능한 Visual C\+\+ 제공 ActiveX 컨트롤 목록은 Visual C\+\+ .NET 제품 CD\-ROM 디스크 2의 Program Files\\Microsoft Visual Studio .NET 2003\\redist.txt를 참조하세요. Win\\System 폴더의 모든 .ocx 파일은 재배포 가능합니다.  
  
 [MFC ActiveX 컨트롤: ActiveX 컨트롤 배포](../../mfc/mfc-activex-controls-distributing-activex-controls.md)에서는 재배포 가능한 ActiveX 컨트롤을 설치하고 등록하는 방법에 대해 설명합니다.  
  
 [병합 모듈 프로젝트](http://msdn.microsoft.com/ko-kr/e92e4f85-fba5-45ee-a432-892a956daeb9)에서는 Visual Studio .NET 배포에서 병합 모듈을 통해 파일의 재배포를 처리하는 방법에 대해 설명합니다.  
  
 [데이터베이스 지원 파일 재배포](../../ide/redistributing-database-support-files.md)에서는 Microsoft Data Access SDK에 포함된 데이터베이스 기술에 대한 지원 파일을 재배포하는 방법에 대해 설명합니다.  
  
 응용 프로그램에서 데이터베이스에 연결하는 ActiveX 컨트롤을 사용하는 경우 다음을 설치하거나 수행해야 합니다.  
  
-   **DCOM for Windows.** Windows 2000 이전 버전의 Windows를 실행하는 모든 컴퓨터에서 Dcom98.exe 또는 Dcom95.exe를 실행해야 합니다. Dcom98.exe는 Windows 98 전용이고, Dcom95.exe는 Windows 95 전용입니다.  
  
-   **MDAC 2.8 SDK.** 대상 컴퓨터에 Microsoft Data Access 2.8 SDK를 설치해야 합니다.[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=205525](http://go.microsoft.com/fwlink/?LinkId=205525)에서 다운로드할 수 있습니다.  
  
-   **MDAC 2.8 재배포 프로그램.** MDAC 2.8 SDK는 MDAC 2.8 재배포 프로그램\(MDAC\_TYP.EXE\)에서 사용하도록 설계되었습니다. MDAC\_TYP.EXE는 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=164412](http://go.microsoft.com/fwlink/?LinkId=164412)에서 다운로드할 수 있습니다.  
  
-   **DSN 복제.** 또한 대상 컴퓨터에 데이터 원본 이름을 복제해야 합니다. 이 작업은 [ConfigDSN](https://msdn.microsoft.com/en-us/library/ms709275.aspx) 같은 함수를 사용하여 프로그래밍 방식으로 수행할 수 있습니다.  
  
## 구성 요소 재배포에 대한 중요 정보  
  
-   **DAO 구성 요소 재배포.** Jet 4.0 SP3\(버전 2927.04\) 이상을 사용하는 것이 좋습니다. Jet 4.0 SP3은 Windows 2000 및 Windows Me와 함께 제공됩니다. 이 버전의 Jet을 사용하면 응용 프로그램에서 테스트해야 하는 Jet 버전 수가 줄어듭니다.  
  
     Windows XP는 이전 버전의 Windows에 포함되지 않은 업그레이드된 서비스 팩 버전의 Jet을 제공합니다. Windows XP에서 응용 프로그램을 테스트하면 Windows XP와 함께 제공된 Jet 버전이 자동으로 테스트됩니다. Jet 4.0의 두 버전에서 DAO 응용 프로그램을 테스트한 후 릴리스해야 합니다.  
  
     Windows XP 버전의 유일한 차이점은 Windows 2000이 릴리스된 이후 발견된 문제에 대한 수정 사항입니다. 응용 프로그램 사용자에게 문제가 발생하지 않으면 Jet 4.0 SP3 이상으로 업그레이드할 필요가 없습니다.  
  
-   **ActiveX 컨트롤의 알려진 문제.** 기술 자료 문서 "PRB: 재배포 가능한 컨트롤의 동적 만들기 실패"\(Q151804\)에 설명된 대로 Visual C\+\+가 설치되지 않은 컴퓨터에 재배포 가능한 ActiveX 컨트롤의 인스턴스를 동적으로 만드는 것과 관련된 알려진 문제가 있습니다. 기술 자료 문서는 MSDN Library CD\-ROM 또는 [http:\/\/support.microsoft.com](http://support.microsoft.com)에서 찾을 수 있습니다. 또한 대화 상자에 일부 ActiveX 컨트롤을 배치하는 것과 관련된 알려진 문제가 있습니다. 기술 자료 문서 "PRB: Microsoft ActiveX 컨트롤에 디자인 타임 라이선스 필요"\(Q155059\)에 설명된 대로 컨트롤에 디자인 타임 라이선스가 필요하다는 메시지 상자가 표시됩니다. 기술 자료 문서는 MSDN Library CD\-ROM 또는 [http:\/\/support.microsoft.com](http://support.microsoft.com)에서 찾을 수 있습니다.  
  
-   **Visual Studio 라이선스가 있는 컨트롤.** Visual Studio 정식 사용자는 다른 Visual Studio 개발 도구와 관련된 추가 ActiveX 컨트롤을 재배포할 수 있습니다. 예를 들어 차트 컨트롤은 Visual Basic과 함께 배포되며, Visual Studio에서도 제공됩니다. 따라서 Visual C\+\+를 Visual Studio 라이선스의 일부로 사용하는 경우 차트 컨트롤을 재배포할 수 있습니다. 그러나 Visual C\+\+만 구매한 경우에는 재배포할 수 있는 라이선스가 없습니다.  
  
## 참고 항목  
 [ActiveX 컨트롤 사용](../../data/ado-rdo/using-activex-controls.md)   
 [MFC ActiveX 컨트롤: ActiveX 컨트롤 배포](../../mfc/mfc-activex-controls-distributing-activex-controls.md)