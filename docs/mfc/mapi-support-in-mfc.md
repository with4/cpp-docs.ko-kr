---
title: MFC의 MAPI 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5d6498d1ecb20b47070cb26bf1a9d732340e266
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349664"
---
# <a name="mapi-support-in-mfc"></a>MFC의 MAPI 지원
MFC의는 Microsoft 응용 프로그램 프로그램 인터페이스 MAPI (메시징) 클래스에 하위 집합에 대 한 지원을 제공 **CDocument**합니다. 특히, **CDocument** 메일 지원 최종 사용자의 컴퓨터에 있는지 여부를 결정 하는 멤버 함수 있으며이 경우에 표준 명령 ID가 하는 메일 보내기 명령을 사용할 **ID_FILE_SEND_MAIL**. 이 명령에 대 한 MFC 처리기 함수에는 사용자가 전자 메일을 통해 문서를 보낼 수 있도록 합니다.  
  
> [!TIP]
>  MFC 전체 MAPI 함수 집합을 캡슐화 되지 않지만 여전히 함수를 호출할 수 MAPI를 직접 MFC 프로그램에서 직접 Win32 API 함수를 호출 합니다.  
  
 메일 보내기 명령을 응용 프로그램에서 매우 쉽습니다. MFC 문서를 패키지 하는 (즉,는 **CDocument**-파생 된 개체)를 첨부 파일로 메일로 보냅니다. 이 첨부 파일은 저장 하는 파일 저장을 명령과 같습니다 (serialize) 메일 메시지에는 문서의 내용을 합니다. 사용자의 컴퓨터에 메일 주소를 지정 하 고 메일 메시지에 주제와 메시지 텍스트를 추가할 수 있는 기회를 사용자에 게 메일 클라이언트에이 구현을 호출 합니다. 사용자가 친숙 한 메일 응용 프로그램의 사용자 인터페이스를 참조 하십시오. 이 기능은 제공한 두 **CDocument** 멤버 함수: `OnFileSendMail` 및 `OnUpdateFileSendMail`합니다.  
  
 MAPI 첨부 파일을 보낼 파일을 읽을 수 있어야 합니다. 이 응용 프로그램은 해당 데이터 파일 중에 열려 있는 경우는 `OnFileSendMail` 함수 호출 여러 프로세스에서 파일에 액세스할 수 있도록 공유 모드로 열려 파일이 있어야 합니다.  
  
> [!NOTE]
>  재정의 버전의 `OnFileSendMail` 클래스에 대 한 `COleDocument` 올바르게 핸들 복합 문서입니다.  
  
#### <a name="to-implement-a-send-mail-command-with-mfc"></a>Mfc는 메일 보내기 명령을 구현 하려면  
  
1.  Visual c + + 메뉴 편집기를 사용 하 여 명령 ID가 메뉴 항목을 추가 하려면 **ID_FILE_SEND_MAIL**합니다.  
  
     이 명령은 ID AFXRES에 프레임 워크에서 제공 됩니다. 8. 이 명령은 모든 메뉴에 추가할 수 있지만 일반적으로에 추가 된 **파일** 메뉴.  
  
2.  문서의 메시지 맵에 다음을 수동으로 추가 합니다.  
  
     [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]  
  
    > [!NOTE]
    >  이 메시지 맵 중 하나에서 파생 된 문서에 대 한 작동 **CDocument** 또는 **COleDocument** -메시지 맵이 파생된 문서 클래스에는 두 경우 모두에 올바른 기본 클래스를 선택 합니다.  
  
3.  응용 프로그램을 작성 합니다.  
  
 MFC 메뉴 항목을 사용 하면 전자 메일 서비스를 사용할 수 있으면 `OnUpdateFileSendMail` 이후에 사용 하 여 명령을 처리 하 고 `OnFileSendMail`합니다. 전자 메일 서비스를 사용할 수 없는 경우 MFC 자동으로 메뉴 항목을 제거 되므로 사용자에 게는 표시 되지 않습니다.  
  
> [!TIP]
>  메시지 맵 항목 앞에서 설명한 대로 수동으로 추가 하는 대신 메시지 함수를 매핑할 클래스의 속성 창을 사용할 수 있습니다. 자세한 내용은 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.  
  
 관련된 정보에 대 한 참조는 [MAPI](../mfc/mapi.md) 개요입니다.  
  
 에 대 한 자세한 내용은 **CDocument** MAPI를 사용 하도록 설정 하는 멤버 함수를 참조 하세요.  
  
-   [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)  
  
-   [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)  
  
-   [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)  
  
## <a name="see-also"></a>참고 항목  
 [MAPI](../mfc/mapi.md)

