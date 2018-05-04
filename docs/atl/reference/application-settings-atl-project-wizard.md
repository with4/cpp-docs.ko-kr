---
title: 응용 프로그램 설정, ATL 프로젝트 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47fbf95451834e5f8c41e8b6d7e5af7a9746bb85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="application-settings-atl-project-wizard"></a>응용 프로그램 설정, ATL 프로젝트 마법사
사용 하 여 **응용 프로그램 설정** 디자인 하 고 새 ATL 프로젝트에 기본 기능을 추가 하는 ATL 프로젝트 마법사의 페이지입니다.  
  
## <a name="server-type"></a>서버 유형  
 세 가지 서버 유형 중 하나를 선택 합니다.  
  
 **동적 연결 라이브러리 (DLL)**  
 프로세스 서버를 만들려면 선택 합니다.  
  
 **실행 (EXE)**  
 로컬 독립 프로세스 서버를 만들려면 선택 합니다. 이 옵션에는 MFC 또는 COM + 1.0에 대 한 지원을 허용 하지 않습니다. 프록시/스텁 코드 병합 허용 하지 않습니다.  
  
 **서비스 (EXE)**  
 Windows가 시작 될 때 백그라운드에서 실행 되는 Windows 응용 프로그램을 만들려면 선택 합니다. 이 옵션 MFC 또는 COM + 1.0에 대 한 지원을 허용 하지 않거나 프록시/스텁 코드 병합을 허용 하지 않습니다.  
  
## <a name="additional-options"></a>추가 옵션  
  
> [!NOTE]
>  모든 추가 옵션은 DLL 프로젝트에만 사용할 수 있습니다.  
  
 **프록시/스텁 코드 병합 허용**  
 선택 된 **프록시/스텁 코드 병합 허용** 인터페이스 마샬링 필요할 때 편의 위해 확인란 합니다. 이 옵션을이 선택 배치 MIDL에서 생성 된 프록시 및 스텁 코드 동일한 서버로 실행 합니다.  
  
 **MFC 지원**  
 개체에 MFC 지원이 포함 되도록 지정 하려면 선택 합니다. 이 옵션 클래스와 포함 하는 함수 중 하나를 액세스할 수 있도록 프로젝트가 MFC 라이브러리에 연결 합니다.  
  
 **COM + 1.0 지원**  
 COM + 1.0 구성 요소를 지원 하기 위해 프로젝트 빌드 설정을 수정 하려면 선택 합니다. 기본 라이브러리 목록 외에 COM + 1.0 구성 요소 관련 라이브러리 comsvcs.lib가 추가 됩니다.  
  
 또한 mtxex.dll은 지연 응용 프로그램이 시작 하는 경우 호스트 시스템에서 로드 됩니다.  
  
-   **구성 요소 등록자 지원** ATL 프로젝트가 지원 COM + 1.0 구성 요소를 포함 하는 경우이 옵션을 설정할 수 있습니다. 구성 요소 관리자는 구성 요소 목록을 가져올, 구성 요소를 등록 또는 구성 요소 (개별적으로 또는 한 번에 모두)의 등록을 취소 하면 COM + 1.0 개체를 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)

