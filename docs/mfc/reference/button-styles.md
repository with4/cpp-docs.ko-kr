---
title: 단추 스타일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BS_DEFPUSHBUTTON
- BS_NOTIFY
- BS_MULTILINE
- BS_AUTOCHECKBOX
- BS_3STATE
- BS_BITMAP
- BS_TOP
- BS_PUSHBUTTON
- BS_PUSHLIKE
- BS_AUTO3STATE
- BS_CHECKBOX
- BS_AUTORADIOBUTTON
- BS_RADIOBUTTON
- BS_OWNERDRAW
- BS_LEFT
- BS_USERBUTTON
- BS_RIGHTBUTTON
- BS_RIGHT
- BS_LEFTTEXT
- BS_TEXT
- BS_BOTTOM
- BS_GROUPBOX
- BS_FLAT
- BS_VCENTER
- BS_ICON
- BS_CENTER
dev_langs:
- C++
helpviewer_keywords:
- BS_NOTIFY constant [MFC]
- BS_RIGHTBUTTON constant [MFC]
- styles [MFC], button objects
- BS_USERBUTTON constant [MFC]
- BS_VCENTER constant [MFC]
- BS_PUSHLIKE constant [MFC]
- BS_RADIOBUTTON constant [MFC]
- BS_PUSHBUTTON constant [MFC]
- BS_DEFPUSHBUTTON constant [MFC]
- BS_LEFTTEXT constant [MFC]
- button objects (CButton), button styles
- BS_AUTO3STATE constant [MFC]
- BS_3STATE constant [MFC]
- BS_OWNERDRAW constant [MFC]
- BS_AUTORADIOBUTTON constant [MFC]
- BS_GROUPBOX constant [MFC]
- BS_BITMAP constant [MFC]
- BS_CENTER constant [MFC]
- BS_MULTILINE constant [MFC]
- BS_BOTTOM constant [MFC]
- BS_FLAT constant [MFC]
- BS_AUTOCHECKBOX constant [MFC]
- BS_RIGHT constant [MFC]
- BS_CHECKBOX constant [MFC]
- BS_LEFT constant [MFC]
- BS_ICON constant [MFC]
- BS_TOP constant [MFC]
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ec945c95b81570e52cca03ed4e52355350d8121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="button-styles"></a>단추 스타일
이 항목에서는 단추 형식 및 스타일에 설명 합니다.  
  
## <a name="button-types"></a>단추 종류  
 다음 표에서 단추 유형을 나열합니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다. 단추 종류를 지정 하지 않으면 기본값은 `BS_PUSHBUTTON`합니다.  
  
|형식|설명|  
|----------|-----------------|  
|`BS_3STATE`|세 가지 상태를 사용 하 여 확인란 단추 만듭니다: `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 소유자 창에 알림 하지만 단추의 상태를 변경 하지 않습니다. 기본적으로 연결 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTO3STATE`|세 가지 상태를 사용 하 여 확인란 단추 만듭니다: `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 소유자 창에 알림 단추의 상태를 변경 합니다. 단추 내용의의 순서는 주기 `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 기본적으로 연결 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTOCHECKBOX`|두 개의 상태를 사용 하 여 확인란 단추 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 소유자 창에 알림 단추의 상태를 변경 합니다. 기본적으로 연결 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTORADIOBUTTON`|두 개의 상태를 사용 하 여 라디오 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 라디오 단추는 일반적으로 각 그룹은 최대 한 번에 하나의 선택 된 옵션을 사용 하 여 그룹에 사용 됩니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 클릭 한 라디오 단추를의 상태를 설정 하는 소유자 창에 알림 `BST_CHECKED`, 단추 그룹의 다른 모든 라디오 단추 상태를 설정 하 고 `BST_UNCHECKED`합니다. 기본적으로 연결 된 텍스트 라디오 단추의 오른쪽에 표시 됩니다. 라디오 단추 왼쪽에 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_CHECKBOX`|두 개의 상태를 사용 하 여 확인란 단추 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 소유자 창에 알림 하지만 단추의 상태를 변경 하지 않습니다. 기본적으로 연결 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_COMMANDLINK`|명령 링크 단추를 만듭니다. 명령 링크 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 주 텍스트와 주 텍스트 아래의 참고의 왼쪽에 녹색 화살표를 표시 하는 합니다. 사용 하 여 메모 텍스트를 설정할 수 있습니다 [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)합니다.|  
|`BS_DEFCOMMANDLINK`|명령 링크 단추를 만듭니다. 명령 링크 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 주 텍스트와 주 텍스트 아래의 참고의 왼쪽에 녹색 화살표를 표시 하는 합니다. 사용 하 여 메모 텍스트를 설정할 수 있습니다 [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)합니다. 대화 상자에 단추가 있으면 보냅니다 키에서 ENTER 키를 누르면는 `BN_CLICKED` 단추에 입력된 포커스가 없는 경우에 대화 상자에는 알림입니다.|  
|`BS_DEFPUSHBUTTON`|중형 검은색 테두리가 있는 명령 단추를 만듭니다. 대화 상자에 단추가 있으면 보냅니다 키에서 ENTER 키를 누르면는 `BN_CLICKED` 단추에 입력된 포커스가 없는 경우에 대화 상자에는 알림입니다.|  
|`BS_DEFSPLITBUTTON`|분할 단추를 만듭니다. 분할 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 단추 옆에 드롭다운 화살표를 포함 하 합니다. 단추를 클릭할 때 기본 명령이 실행 됩니다. 드롭다운 화살표를 클릭 하면 추가 명령이 메뉴가 나타납니다. 분할 단추는 대화 상자에 있으면 보냅니다 키에서 ENTER 키를 누르면는 `BN_CLICKED` 단추에 입력된 포커스가 없는 경우에 대화 상자에 게 알림|  
|`BS_GROUPBOX`|다른 단추를 그룹화 할 수 있는 사각형을 만듭니다. 이 스타일과 관련 된 텍스트 사각형의 왼쪽 위 모서리에 표시 됩니다.|  
|`BS_OWNERDRAW`|소유자가 그린 단추를 만듭니다. 호출 하 여 프레임 워크는 `DrawItem` 메서드 때 단추의 시각적 측면이 변경 되었습니다. 사용 하는 경우이 스타일을 설정 해야 합니다는 `CBitmapButton` 클래스입니다.|  
|`BS_PUSHBUTTON`|전송 하는 명령 단추를 만듭니다는 `BN_CLICKED` 알림 창을 사용자가 단추를 클릭 합니다.|  
|`BS_RADIOBUTTON`|두 개의 상태를 사용 하 여 라디오 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 라디오 단추는 일반적으로 각 그룹은 최대 한 번에 하나의 선택 된 옵션을 사용 하 여 그룹에 사용 됩니다. 단추를 클릭 하면 전송는 `BN_CLICKED` 알림 소유자 창에 있지만 그룹의 모든 단추의 상태를 자동으로 바뀌지 않습니다. 기본적으로 연결 된 텍스트 라디오 단추의 오른쪽에 표시 됩니다. 라디오 단추 왼쪽에 텍스트를 표시 하려면 사용 하 여는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_SPLITBUTTON`|분할 단추를 만듭니다. 분할 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 단추 옆에 드롭다운 화살표를 포함 하 합니다. 단추를 클릭할 때 기본 명령이 실행 됩니다. 드롭다운 화살표를 클릭 하면 추가 명령이 메뉴가 나타납니다.|  
|`BS_USERBUTTON`|16 비트 버전의 Windows와의 호환성을 제공 하지만 사용 합니다. Win32 기반 응용 프로그램을 사용할지 `BS_OWNERDRAW` 대신 합니다.|  
  
## <a name="radio-button-and-check-box-styles"></a>라디오 단추 및 확인란 스타일  
 다음 표에서 라디오 단추 및 확인란에만 적용 되는 스타일을 보여 줍니다. 이러한 스타일은 모든 다른 종류의 단추에서 무시 됩니다. 필요에 따라 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|라디오 단추 또는 확인란 스타일을 함께 사용 하면 텍스트 라디오 단추 또는 확인란의 왼쪽에 나타납니다.|  
|`BS_RIGHTBUTTON`|라디오 단추 또는 확인란 스타일을 함께 사용 하면 텍스트 라디오 단추 또는 확인란의 왼쪽에 나타납니다. 이 스타일은 동일는 `BS_LEFTTEXT` 스타일입니다.|  
|`BS_PUSHLIKE`|사용 확인란 또는 라디오 단추 모양 및 명령 단추 처럼 동작 합니다. 상태가 때 나타나므로 누름 `BST_CHECKED`누른 마우스 상태를 흐리게 표시 `BST_INDETERMINATE`때 상태를 해제 하 고 `BST_UNCHECKED`합니다.|  
  
## <a name="text-alignment-styles"></a>텍스트 맞춤 스타일입니다.  
 다음 표에서 가로 및 세로 텍스트 맞춤 옵션을 보여 줍니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_LEFT`|왼쪽 단추 사각형에 텍스트를 맞춥니다. 그러나 단추는 확인란 또는 라디오 단추는 없는 경우는 `BS_RIGHTBUTTON` 스타일 텍스트 왼쪽의 확인란 또는 라디오 단추 오른쪽에 정렬 합니다.|  
|`BS_RIGHT`|오른쪽 단추 사각형에 텍스트를 맞춥니다. 그러나 단추는 확인란 또는 라디오 단추는 없는 경우는 `BS_RIGHTBUTTON` 스타일을 텍스트는 올바른 확인란 또는 라디오 단추 오른쪽에 맞춰집니다.|  
|`BS_CENTER`|단추 사각형의 가로 텍스트를 가운데에 맞춥니다.|  
|`BS_TOP`|텍스트는 단추 사각형의 위쪽에 배치합니다.|  
|`BS_BOTTOM`|단추 사각형의 아래쪽에 텍스트를 배치합니다.|  
|`BS_VCENTER`|단추 사각형에 세로로 텍스트를 가운데 맞춤합니다.|  
  
## <a name="button-content-options"></a>단추 콘텐츠 옵션  
 다음 표에서 단추에 표시할 항목을 나타내는 옵션을 보여 줍니다. 텍스트를 표시 하기만 하는 단추 형식이 스타일을 무시 합니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_BITMAP`|비트맵 단추에 표시 되는지 지정 합니다.|  
|`BS_ICON`|단추 아이콘을 표시를 지정 합니다.|  
|`BS_TEXT`|단추 텍스트를 표시를 지정 합니다.|  
  
## <a name="other-options"></a>기타 옵션  
 다음 표에서 모든 단추 유형과 함께 사용할 수 있는 추가 옵션을 보여 줍니다. 필요에 따라 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_FLAT`|단추는 2 차원 및 3 차원 이미지를 만들려면 기본 음영으로 그리지 않습니다 지정 합니다.|  
|`BS_MULTILINE`|텍스트 문자열이 너무 길어 단추 사각형에 한 줄 인지 여러 줄으로 단추 텍스트를 래핑합니다.|  
|`BS_NOTIFY`|보낼 단추를 활성화 `BN_DBLCLK`, `BN_KILLFOCUS`, 및 `BN_SETFOCUS` 알림 메시지를 해당 부모 창입니다. 보내기 단추는 `BN_CLICKED` 이 스타일 지정 되었는지 여부에 관계 없이 알림입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create) [단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951)   



