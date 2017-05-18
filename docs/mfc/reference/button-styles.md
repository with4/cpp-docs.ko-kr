---
title: "단추 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
- BS_NOTIFY constant
- BS_RIGHTBUTTON constant
- styles, button objects
- BS_USERBUTTON constant
- BS_VCENTER constant
- BS_PUSHLIKE constant
- BS_RADIOBUTTON constant
- BS_PUSHBUTTON constant
- BS_DEFPUSHBUTTON constant
- BS_LEFTTEXT constant
- button objects (CButton), button styles
- BS_AUTO3STATE constant
- BS_3STATE constant
- BS_OWNERDRAW constant
- BS_AUTORADIOBUTTON constant
- BS_GROUPBOX constant
- BS_BITMAP constant
- BS_CENTER constant
- BS_MULTILINE constant
- BS_BOTTOM constant
- BS_FLAT constant
- BS_AUTOCHECKBOX constant
- BS_RIGHT constant
- BS_CHECKBOX constant
- BS_LEFT constant
- BS_ICON constant
- BS_TOP constant
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cdd577cd6915a1f3c1e05fae68f7fed47cc79236
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="button-styles"></a>단추 스타일
이 항목에서는 단추 형식 및 스타일에 설명 합니다.  
  
## <a name="button-types"></a>단추 종류  
 다음 표에서 단추 유형을 나열합니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다. 단추 종류를 지정 하지 않으면 기본값은 `BS_PUSHBUTTON`합니다.  
  
|형식|설명|  
|----------|-----------------|  
|`BS_3STATE`|세 가지 상태를 사용 하 여 확인란 단추를 만듭니다: `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 하지만 단추의 상태를 변경 하지 않습니다. 기본적으로 관련 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 된 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTO3STATE`|세 가지 상태를 사용 하 여 확인란 단추를 만듭니다: `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 단추의 상태를 변경 합니다. 단추 내용의의 순서는 주기 `BST_CHECKED`, `BST_INDETERMINATE`, 및 `BST_UNCHECKED`합니다. 기본적으로 관련 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 된 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTOCHECKBOX`|두 개의 상태를 사용 하 여 확인란 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 단추의 상태를 변경 합니다. 기본적으로 관련 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 된 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_AUTORADIOBUTTON`|두 개의 상태를 사용 하 여 라디오 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 라디오 단추는 일반적으로 각 그룹은 최대 한 번에 하나의 선택된 옵션을 사용 하 여 그룹에 사용 됩니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 클릭 한 라디오 단추를의 상태를 설정 `BST_CHECKED`, 단추 그룹의 다른 모든 라디오 단추 상태를 설정 하 고 `BST_UNCHECKED`합니다. 기본적으로 관련 된 텍스트는 오른쪽의 라디오 단추에 표시 됩니다. 사용 하 여 텍스트 왼쪽에 있는 라디오 단추를 표시 하려면는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_CHECKBOX`|두 개의 상태를 사용 하 여 확인란 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 하지만 단추의 상태를 변경 하지 않습니다. 기본적으로 관련 된 텍스트의 확인란 오른쪽에 표시 됩니다. 왼쪽의 확인란의 텍스트를 표시 하려면 사용 된 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_COMMANDLINK`|명령 링크 단추를 만듭니다. 명령 링크 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 주 텍스트와 주 텍스트 아래 메모의 왼쪽에 녹색 화살표가 표시입니다. 사용 하 여 메모 텍스트를 설정할 수 있습니다 [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)합니다.|  
|`BS_DEFCOMMANDLINK`|명령 링크 단추를 만듭니다. 명령 링크 단추는 관련 명령 단추 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 주 텍스트와 주 텍스트 아래 메모의 왼쪽에 녹색 화살표가 표시입니다. 사용 하 여 메모 텍스트를 설정할 수 있습니다 [CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)합니다. 대화 상자에 단추가 경우 보냅니다 키에서 ENTER 키를 눌러는 `BN_CLICKED` 입력된 포커스가 있는 단추에 없는 경우에 대화 상자에는 알림입니다.|  
|`BS_DEFPUSHBUTTON`|중형 검은색 테두리가 있는 명령 단추를 만듭니다. 대화 상자에 단추가 경우 보냅니다 키에서 ENTER 키를 눌러는 `BN_CLICKED` 입력된 포커스가 있는 단추에 없는 경우에 대화 상자에는 알림입니다.|  
|`BS_DEFSPLITBUTTON`|분할 단추를 만듭니다. 분할 단추는 명령 단추에 특정 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 단추 옆에 드롭다운 화살표를 포함 하는 합니다. 단추를 클릭할 때 기본 명령이 실행 됩니다. 드롭다운 화살표를 클릭 하면 추가 명령이 메뉴가 나타납니다. 분할 단추는 대화 상자에 있으면 보냅니다 키에서 ENTER 키를 눌러는 `BN_CLICKED` 입력된 포커스가 있는 단추에 없는 경우에 대화 상자에 알림|  
|`BS_GROUPBOX`|다른 단추를 그룹화 할 수 있는 사각형을 만듭니다. 이 스타일과 관련 된 텍스트 사각형의 왼쪽 위 모퉁이에 표시 됩니다.|  
|`BS_OWNERDRAW`|소유자가 그린 단추를 만듭니다. 프레임 워크 호출의 `DrawItem` 메서드가 때 단추의 시각적 측면이 변경 되었습니다. 사용 하는 경우이 스타일을 설정 해야는 `CBitmapButton` 클래스입니다.|  
|`BS_PUSHBUTTON`|전송 하는 명령 단추를 만듭니다를 `BN_CLICKED` 알림 창을 사용자가 단추를 클릭 합니다.|  
|`BS_RADIOBUTTON`|두 개의 상태를 사용 하 여 라디오 단추를 만듭니다: `BST_CHECKED` 및 `BST_UNCHECKED`합니다. 라디오 단추는 일반적으로 각 그룹은 최대 한 번에 하나의 선택된 옵션을 사용 하 여 그룹에 사용 됩니다. 전송 단추를 클릭 하는 `BN_CLICKED` 소유자 창에 알림을 하지만 자동으로 그룹의 모든 단추의 상태를 변경 하지 않습니다. 기본적으로 관련 된 텍스트는 오른쪽의 라디오 단추에 표시 됩니다. 사용 하 여 텍스트 왼쪽에 있는 라디오 단추를 표시 하려면는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일입니다.|  
|`BS_SPLITBUTTON`|분할 단추를 만듭니다. 분할 단추는 명령 단추에 특정 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] 단추 옆에 드롭다운 화살표를 포함 하는 합니다. 단추를 클릭할 때 기본 명령이 실행 됩니다. 드롭다운 화살표를 클릭 하면 추가 명령이 메뉴가 나타납니다.|  
|`BS_USERBUTTON`|16 비트 버전의 Windows와 호환성을 위해 제공 되지만 사용 합니다. Win32 기반 응용 프로그램을 사용 해야 `BS_OWNERDRAW` 대신 합니다.|  
  
## <a name="radio-button-and-check-box-styles"></a>라디오 단추 및 확인란 스타일  
 다음 표에서 라디오 단추 및 확인란에만 적용 되는 스타일을 나열 합니다. 이러한 스타일은 모든 다른 종류의 단추에서 무시 됩니다. 필요에 따라 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|라디오 단추 또는 확인란 스타일을 함께 사용 하면 텍스트는 라디오 단추 또는 확인란의 왼쪽에 나타납니다.|  
|`BS_RIGHTBUTTON`|라디오 단추 또는 확인란 스타일을 함께 사용 하면 텍스트는 라디오 단추 또는 확인란의 왼쪽에 나타납니다. 이 스타일은 동일는 `BS_LEFTTEXT` 스타일입니다.|  
|`BS_PUSHLIKE`|확인란 또는 라디오 단추 명령 단추 처럼 보이고 작동 만듭니다. 때이 단추 누름 상태는 `BST_CHECKED`를 누르면 해당 상태는 흐리게 표시 `BST_INDETERMINATE`, 해당 상태 경우 출시 `BST_UNCHECKED`합니다.|  
  
## <a name="text-alignment-styles"></a>텍스트 맞춤 스타일  
 다음 표에서 가로 및 세로 텍스트 맞춤 옵션을 보여 줍니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_LEFT`|왼쪽 단추 사각형에 텍스트를 맞춥니다. 그러나 단추는 확인란 또는 라디오 단추는 없는 경우는 `BS_RIGHTBUTTON` 스타일과 텍스트 왼쪽의 확인란 또는 라디오 단추 오른쪽에 정렬 합니다.|  
|`BS_RIGHT`|오른쪽 단추 사각형에 텍스트를 맞춥니다. 그러나 단추는 확인란 또는 라디오 단추는 없는 경우는 `BS_RIGHTBUTTON` 스타일을 텍스트는 오른쪽 확인란 또는 라디오 단추 오른쪽에 맞춰집니다.|  
|`BS_CENTER`|가로로 단추 사각형의 텍스트를 가운데 맞춤 됩니다.|  
|`BS_TOP`|단추 사각형의 위쪽에 텍스트를 배치합니다.|  
|`BS_BOTTOM`|단추 사각형의 아래쪽에 텍스트를 배치합니다.|  
|`BS_VCENTER`|단추 사각형에 세로로 텍스트를 가운데 맞춤 됩니다.|  
  
## <a name="button-content-options"></a>단추 콘텐츠 옵션  
 다음 표에서 단추에 표시 되는 내용을 나타내는 옵션을 나열 합니다. 단추 종류만 텍스트를 표시 하는 이러한 스타일을 무시 합니다. 필요에 따라 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_BITMAP`|비트맵 단추에 표시 되도록 지정 합니다.|  
|`BS_ICON`|단추 아이콘을 표시를 지정 합니다.|  
|`BS_TEXT`|단추 텍스트를 표시 하도록 지정 합니다.|  
  
## <a name="other-options"></a>기타 옵션  
 다음 표에서 단추 종류와 사용할 수 있는 추가 옵션을 나열 합니다. 필요에 따라 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|-----------|-----------------|  
|`BS_FLAT`|단추는&2; 차원 및&3; 차원 이미지를 만드는 기본 음영을 사용 하 여 그린 하지 지정 합니다.|  
|`BS_MULTILINE`|단추 사각형에 한 줄에 맞게 텍스트 문자열이 너무 깁니다. 여러 줄으로 단추 텍스트를 래핑합니다.|  
|`BS_NOTIFY`|보낼 단추를 활성화 `BN_DBLCLK`를 `BN_KILLFOCUS`를 및 `BN_SETFOCUS` 알림 메시지를 해당 부모 창입니다. 보내기 단추에 `BN_CLICKED` 이 스타일 지정 되었는지 여부에 관계 없이 알림.|  
  
## <a name="see-also"></a>참고 항목  
 [MFC에서 사용 되는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create)
 [단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951)   




