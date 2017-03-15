---
title: "MFC DLL 마법사, 응용 프로그램 설정 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: df1e3de3e1548fe4c4c340a30127d9916998ba64
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-mfc-dll-wizard"></a>MFC DLL 마법사, 응용 프로그램 설정
MFC DLL 마법사의이 페이지를 사용 하 여 설계 하 고 새 MFC DLL 프로젝트에 기본 기능을 추가 합니다.  
  
## <a name="dll-type"></a>DLL 종류  
 만들려는 DLL의 유형을 선택 합니다.  
  
 **공유 MFC DLL을 사용 하 여 기본 DLL**  
 MFC 라이브러리를 공유 DLL로 프로그램에 연결 하려면이 옵션을 선택 합니다. 이 옵션을 사용 하면 DLL과 호출 응용 프로그램 간에 MFC 개체를 공유할 수 없습니다. 프로그램에서는 런타임에 MFC 라이브러리를 호출 합니다. 이 옵션의 MFC 라이브러리를 사용 하는 여러 개의 실행 파일 구성 된 경우 프로그램의 디스크 및 메모리 요구 사항이 줄어듭니다. W i n&32;와 MFC 프로그램 DLL의 함수를 호출할 수 있습니다. 이러한 유형의 프로젝트를 사용 하 여 MFC DLL을 재배포 해야 합니다.  
  
 **기본 DLL MFC에 정적으로 연결합니다.**  
 빌드 타임에 정적으로 MFC 라이브러리에 프로그램을 연결 하려면이 옵션을 선택 합니다. W i n&32;와 MFC 프로그램 DLL의 함수를 호출할 수 있습니다. 이 옵션은 프로그램의 크기를 늘립니다, 이러한 유형의 프로젝트를 사용 하 여 MFC DLL을 재배포할 필요가 없습니다. DLL에서 호출 응용 프로그램 사이의 MFC 개체를 공유할 수 없습니다.  
  
 **MFC 확장 DLL**  
 프로그램 실행 시 MFC 라이브러리를 호출 하 고 DLL과 호출 응용 프로그램 사이 MFC 개체를 공유 하려는 경우이 옵션을 선택 합니다. 이 옵션의 MFC 라이브러리를 사용 하는 여러 개의 실행 파일의 구성 된 경우 프로그램의 디스크 및 메모리 요구 사항이 줄어듭니다. MFC 프로그램만 DLL의 함수를 호출할 수 있습니다. 이러한 유형의 프로젝트를 사용 하 여 MFC DLL을 재배포 해야 합니다.  
  
## <a name="additional-features"></a>추가 기능  
 MFC DLL의 자동화 지원 여부 및 Windows 소켓을 지원 해야 하는지 여부를 선택 합니다.  
  
 **자동화**  
 선택 **자동화** 를 프로그램에서 다른 응용 프로그램에서 구현 되는 개체를 조작할 수 있도록 합니다. 선택 하면 **자동화** 도 다른 자동화 클라이언트에 프로그램을 노출 합니다. 참조 [자동화](../../mfc/automation.md) 에 대 한 자세한 내용은 합니다.  
  
 **Windows 소켓**  
 프로그램 Windows 소켓을 지원 하는지 나타내려면이 옵션을 선택 합니다. Windows 소켓에는 TCP/IP 네트워크를 통해 통신 하는 프로그램을 작성할 수 있습니다.  
  
 Windows와 MFC DLL에서 소켓 지원을 만들어지면 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 초기화 소켓에 대 한 지원 및 MFC 헤더 파일 StdAfx.h AfxSock.h를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL 프로젝트 만들기](../../mfc/reference/creating-an-mfc-dll-project.md)


