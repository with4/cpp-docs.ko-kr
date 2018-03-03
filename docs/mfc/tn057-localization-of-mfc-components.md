---
title: "TN057: MFC 구성 요소 지역화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.components
dev_langs:
- C++
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e27b737a76b30e7193a9afb7797a20951294032e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: MFC 구성 요소 지역화
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 디자인 및 응용 프로그램 또는 OLE 제어 하는 경우 구성 요소, 필드를 지역화 사용할 수 있는 절차 또는 MFC를 사용 하는 DLL의 일부를 설명 합니다.  
  
## <a name="overview"></a>개요  
 실제로 두 가지 문제를 해결 하는 경우 해야 MFC를 사용 하는 구성 요소를 지역화 합니다. 리소스를 지역화 해야 먼저-문자열과 대화 상자, 구성 요소에 관련 된 다른 리소스입니다. 또한 MFC를 사용 하 여 작성 된 대부분의 구성 요소를 포함 하 고 다양 한 MFC에서 정의한 리소스를 사용 합니다. 지역화 된 MFC 리소스를 제공 해야 합니다. 에서는 몇 가지 언어 자체 MFC에서 이미 제공 됩니다.  
  
 또한 대상 환경 (유럽 또는 DBCS 사용이 가능한 환경)에서 실행 되도록 구성 요소를 준비 해야 합니다. 대부분의 경우 올바르게 높은 비트 세트를 가진 문자를 처리 하는 방법 및 더블 바이트 문자를 사용 하 여 문자열 처리 응용 프로그램에 따라 다릅니다. MFC 기능이 경우 기본적으로 이러한 환경은 둘 다에 대 한 설치 시에 연결 하는 다른 리소스와 함께 모든 플랫폼에서 사용 되는 단일 전 세계 바이너리를 할 수 있도록 합니다.  
  
## <a name="localizing-your-components-resources"></a>구성 요소의 리소스 지역화  
 응용 프로그램 또는 DLL 지역화 대상 언어와 일치 하는 리소스는 리소스를 교체 하기만 참여 시켜야 합니다. 사용자 고유의 리소스에 대 한이 작업은 비교적 간단: 리소스 편집기에서 리소스를 편집 하 고 응용 프로그램을 작성 합니다. 코드를 작성 한 경우 제대로 없는 문자열 또는 텍스트를 지역화할 하드 코드 된 c + + 소스 코드-에 됩니다 모든 지역화 단순히 리소스를 수정 하 여 수행할 수 있습니다. 실제로 모든 지역화 된 버전을 제공 하 포함 하지 않는 원본 코드의 빌드 되도록 구성 요소를 구현할 수 있습니다. 이 더 복잡 하지만 중요 한 일입니다 이며 메커니즘을 MFC 자체에 대 한 선택 합니다. 리소스 편집기에 EXE 또는 DLL 파일을 로드 하는 리소스를 직접 편집 하 여 응용 프로그램을 지역화할 수 이기도 합니다. 가능한 하는 동안 이러한 변경 내용 다시 새 버전의 응용 프로그램을 빌드할 때마다 필요 합니다.  
  
 이 문제는 한 가지 방법은 위성 DLL이 라고도 하는 별도 DLL 리소스를 모두 찾는 것입니다. 이 DLL은 런타임에 동적으로 로드 한 다음 및 모든 코드와 함께 주 모듈에서 대신 해당 DLL에서 로드 되는 리소스입니다. MFC는이 방법을 직접 지원합니다. MYAPP 라는 응용 프로그램을 고려 합니다. EXE; MYRES 이라는 DLL에 있는 해당 리소스를 모두가지고 있습니다. DLL입니다. 응용 프로그램의 `InitInstance` 해당 DLL을 로드 하 고 mfc 해당 위치에서 리소스를 로드 하려면 다음을 수행 합니다.  
  
```  
CMyApp::InitInstance()  
{ *// one of the first things in the init code  
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)  
    AfxSetResourceHandle(hInst);

 *// other initialization code would follow  
 .  
 .  
 .  
}  
```  
  
 이제부터 MFC myapp.exe 대신 해당 DLL에서 리소스를 로드 합니다. 그러나 모든 리소스를에 존재 해야 해당 DLL; MFC는 지정된 된 리소스를 찾기 위해 응용 프로그램의 인스턴스를 검색 하지 않습니다. 이 기술은 OLE 컨트롤 뿐 아니라 동일 하 게에 일반 MFC Dll에 적용합니다. 설치 프로그램 MYRES의 적절 한 버전을 복사 합니다. 사용자가 원하는 어떤 리소스 로케일에 따라 DLL입니다.  
  
 상대적으로 리소스를 만드는 쉽게 DLL만 합니다. DLL 프로젝트를 만들고, 추가 하 여 합니다. RC 파일, 선택한 필요한 리소스를 추가 합니다. 이 기술을 사용 하지 않는 기존 프로젝트를 사용 하도록 설정한 경우에 해당 프로젝트에서 리소스를 복사할 수 있습니다. 리소스 파일을 프로젝트에 추가한 후 준비가 거의 프로젝트를 빌드합니다. 수행 해야 하는 유일한 사항은 링커를 포함 하는 옵션 설정 **/NOENTRY**합니다. 이 링커에 지시할 수 DLL 진입점이 없는-에 진입점에 없는 코드에 있기 때문입니다.  
  
> [!NOTE]
>  Visual c + + 4.0 이상 버전에서는 리소스 편집기 당 여러 언어를 지원합니다. RC 파일입니다. 이 수 쉽게 매우 단일 프로젝트에서 프로그램 지역화를 관리할 수 있습니다. 각 언어에 대 한 리소스는 리소스 편집기에서 생성 하는 전처리기 지시문에 의해 제어 됩니다.  
  
## <a name="using-the-provided-mfc-localized-resources"></a>제공 된 MFC를 사용 하 여 지역화 된 리소스  
 MFC에서 다음 두 가지 작성 하는 모든 MFC 응용 프로그램을 다시 사용: 코드 및 리소스. 즉, MFC는 다양 한 오류 메시지, 기본 제공 대화 상자 및 MFC 클래스에서 사용 되는 기타 리소스에 있습니다. 응용 프로그램을 완전히 지역화 하려면 응용 프로그램의 리소스 뿐만 아니라 MFC에서 직접 제공 되는 리소스를 지역화 해야 합니다. MFC는 다양 한 다른 언어 리소스 파일 자동으로 대상으로 하는 언어 MFC에서 이미 지 원하는 언어 중 하나일 경우 하기만 하면 지역화 된 리소스를 사용 하려면 있도록 있습니다.  
  
 이 문서의 작성일 MFC 중국어, 독일어, 스페인어, 프랑스어, 이탈리아어, 일본어 및 한국어를 지원합니다. 이러한 지역화 된 버전을 포함 하는 파일은는 MFC\INCLUDE\L.* ('L'은 지역화에 대 한) 디렉터리입니다. 독일 파일 MFC\INCLUDE\L.DEU, 예를 들어 있습니다. MFC\INCLUDE에 있는 파일 대신 RC 이러한 파일을 사용 하도록 응용 프로그램을 추가 `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` RC 명령줄에 (이 예 시일 뿐; 선택 항목 뿐만 아니라 Visual C을 설치한 디렉터리의 사용자 로캘을 대체 해야 합니다. ++).  
  
 위의 지침에 따라 응용 프로그램이 MFC를 정적으로 링크 하는 경우에 작동 합니다. 대부분의 응용 프로그램 동적으로 (이기 때문에 응용 프로그램 마법사에서 기본값)에 연결 합니다. 이 시나리오에서는 뿐만 아니라 코드를 동적으로 리소스를 되므로-연결 합니다. 결과적으로, 응용 프로그램의 리소스를 지역화할 수 있지만 MFC 구현 리소스 로드 됩니다는 MFC7x.DLL (또는 이후 버전) 또는 MFC7xLOC.DLL 있는 경우. 두 개의 다른 관점에서이 높일 수 있습니다.  
  
 더 복잡 한 방식은 배송 지역화 MFC7xLOC.DLLs 중 하나 (예: MFC7xDEU 독일어, 스페인어, 등 MFC7xESP.DLL) 또는 이후 버전을 응용 프로그램을 설치할 때 적절 한 MFC7xLOC.DLL 시스템 디렉터리에 설치 합니다. 이 개발자와 최종 사용자 모두에 대 한 매우 복잡할 수 있으며 따라서 권장 되지 않습니다. 참조 [기술 참고 56](../mfc/tn056-installation-of-localized-mfc-components.md) 이 기술 및 해당 주의 사항에 대 한 자세한 내용은 합니다.  
  
 응용 프로그램 또는 DLL 자체 (또는 해당 위성 DLL 하나를 사용 하는 경우)에 지역화 된 MFC 리소스를 포함 하는 가장 간단 하 고 안전한 방법이입니다. MFC7xLOC.DLL 제대로 설치의 문제를 방지 합니다. 이렇게 하려면,에서 정적 경우 위에 (지역화 된 리소스를 가리키도록 적절 하 게 RC 명령줄 설정)에 대 한 동일한 지침에 따라를 제외 하 고도 제거 해야 하는 `/D_AFXDLL` 정의 하는 응용 프로그램 마법사가 추가 되었습니다. 때 `/D_AFXDLL` 가 AFXRES를 정의 합니다. H (및 다른 MFC RC 파일) 정의 하지 않습니다 실제로 리소스 (하기 때문에 이러한에서 가져와서 MFC Dll 대신).  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

