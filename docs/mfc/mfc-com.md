---
title: MFC COM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MFC COM (MFC)
dev_langs: C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 652e299ad7dc01f070e3fe4ed9738fc9ed47a493
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-com"></a>MFC COM
액티브 템플릿 라이브러리 (ATL)의 대부분이 설계 된 반면 MFC의 하위 집합 COM 지원 하도록 되어 COM 프로그래밍에 대 한 합니다. 이 항목의이 단원 com MFC의 지원을 설명합니다  
  
 액티브 기술 (예: ActiveX 컨트롤, 액티브 문서 포함, OLE 및 등) 구성 요소 개체 모델 (COM)를 사용 하 여 것 된 언어에 상관 없이 네트워크 환경에서 서로 상호 작용 하는 소프트웨어 구성 요소를 사용 하도록 설정 하려면 만들어집니다. 액티브 기술 바탕 화면 또는 인터넷에서 실행 되는 응용 프로그램을 만드는 데 사용할 수 있습니다. 자세한 내용은 참조 [COM 소개](../atl/introduction-to-com.md) 또는 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)합니다.  
  
 다음을 포함 하는 기술을 클라이언트와 서버 모두 포함 하는 액티브 기술:  
  
-   [액티브 문서 포함](../mfc/active-document-containment.md), MFC 버전 4.2에서에서 지원 및 이상 버전에서는 사용자가 허용 [액티브 문서](../mfc/active-documents.md) (예: Microsoft Excel 또는 Word 파일) 전체 문서의 네이티브 인터페이스를 활성화 하 고 응용 프로그램의 전체 클라이언트 영역에는 [액티브 문서 컨테이너](../mfc/active-document-containers.md) Microsoft Office Binder 또는 Microsoft Internet Explorer와 같은 합니다. 컨테이너 클라이언트 역할을 문서에서 제공 하는 동안 [액티브 문서 서버](../mfc/active-document-servers.md)합니다. 활성 문서를 사용 하 여 인터넷 응용 프로그램에 대 한 자세한 내용은 참조 하세요.: [인터넷의 액티브 문서](../mfc/active-documents-on-the-internet.md)합니다.  
  
-   ActiveX 컨트롤은 웹 사이트와 같은 컨테이너에서 사용할 수 있는 대화형 개체입니다. ActiveX 컨트롤에 대 한 자세한 내용은 다음을 참조 하세요.  
  
    -   [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)  
  
    -   [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)  
  
    -   [개요: 인터넷](../mfc/mfc-internet-programming-basics.md)  
  
    -   [인터넷에서 사용할 기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [ActiveX 컨트롤 디버깅](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   액티브 스크립팅 제어 브라우저 또는 서버에서 하나 이상의 ActiveX 컨트롤의 동작을 통합된 합니다. 액티브 스크립트에 대 한 자세한 내용은 참조 하십시오. [인터넷의 액티브 기술](../mfc/active-technology-on-the-internet.md)합니다.  
  
-   [자동화](../mfc/automation.md) (이전의 OLE 자동화) 다른 응용 프로그램에서 구현 되는 개체를 조작 하거나 "개체를 노출 하" 조작할 수 있도록 한 응용 프로그램에 대 한 가능 하 게 합니다.  
  
     자동화 개체는 로컬 일 수 있습니다 또는 [원격](../mfc/remote-automation.md) 다른 컴퓨터에서 네트워크를 통해 액세스할 수 있습니다. 자동화는 OLE 및 COM 개체 모두에 대해 사용할 수 있습니다.  
  
-   또한이 섹션의 예를 들어, MFC를 사용 하 여 COM 구성 요소를 작성 하는 방법에 정보를 제공 [연결점](../mfc/connection-points.md)합니다.  
  
 에 항목을 참조 여전히 섞어 OLE 액티브 기술 섞어 이제와 논의 [OLE](../mfc/ole-in-mfc.md)합니다.  
  
 참고: 기술 자료 문서 Q248019: 방법: 방지 서버 사용 중 대화 상자에서 표시 되는 동안 정도 시간이 오래 걸리는 COM 작업 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [활성 문서 포함](../mfc/active-document-containment.md)  
  
 [자동화](../mfc/automation.md)  
  
 [원격 자동화](../mfc/remote-automation.md)  
  
 [연결 지점](../mfc/connection-points.md)  
  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)

