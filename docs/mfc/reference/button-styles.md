---
title: "단추 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BS_DEFPUSHBUTTON"
  - "BS_NOTIFY"
  - "BS_MULTILINE"
  - "BS_AUTOCHECKBOX"
  - "BS_3STATE"
  - "BS_BITMAP"
  - "BS_TOP"
  - "BS_PUSHBUTTON"
  - "BS_PUSHLIKE"
  - "BS_AUTO3STATE"
  - "BS_CHECKBOX"
  - "BS_AUTORADIOBUTTON"
  - "BS_RADIOBUTTON"
  - "BS_OWNERDRAW"
  - "BS_LEFT"
  - "BS_USERBUTTON"
  - "BS_RIGHTBUTTON"
  - "BS_RIGHT"
  - "BS_LEFTTEXT"
  - "BS_TEXT"
  - "BS_BOTTOM"
  - "BS_GROUPBOX"
  - "BS_FLAT"
  - "BS_VCENTER"
  - "BS_ICON"
  - "BS_CENTER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BS_3STATE 상수"
  - "BS_AUTO3STATE 상수"
  - "BS_AUTOCHECKBOX 상수"
  - "BS_AUTORADIOBUTTON 상수"
  - "BS_BITMAP 상수"
  - "BS_BOTTOM 상수"
  - "BS_CENTER 상수"
  - "BS_CHECKBOX 상수"
  - "BS_DEFPUSHBUTTON 상수"
  - "BS_FLAT 상수"
  - "BS_GROUPBOX 상수"
  - "BS_ICON 상수"
  - "BS_LEFT 상수"
  - "BS_LEFTTEXT 상수"
  - "BS_MULTILINE 상수"
  - "BS_NOTIFY 상수"
  - "BS_OWNERDRAW 상수"
  - "BS_PUSHBUTTON 상수"
  - "BS_PUSHLIKE 상수"
  - "BS_RADIOBUTTON 상수"
  - "BS_RIGHT 상수"
  - "BS_RIGHTBUTTON 상수"
  - "BS_TEXT 상수"
  - "BS_TOP 상수"
  - "BS_USERBUTTON 상수"
  - "BS_VCENTER 상수"
  - "단추 개체(CButton), 단추 스타일"
  - "스타일, 단추 개체"
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
caps.latest.revision: 20
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단추 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 단추 형식과 스타일을 설명합니다.  
  
## 단추 종류  
 다음 표에는 단추 형식이 나와 있습니다.  옵션으로 다음 중 하나를 선택할 수 있습니다.  버튼 형식을 지정하지 않으면 기본값은  `BS_PUSHBUTTON`입니다.  
  
|형식|설명|  
|--------|--------|  
|`BS_3STATE`|`BST_CHECKED`, `BST_INDETERMINATE`,  `BST_UNCHECKED`의 세 가지 상태의 확인란 단추를 만듭니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지지만 단추 상태는 변경되지 않습니다.  기본적으로, 관련 텍스트가 확인란 오른쪽에 표시됩니다.  확인란의 왼쪽에 텍스트를 표시하려면 사용하는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_AUTO3STATE`|`BST_CHECKED`, `BST_INDETERMINATE`,  `BST_UNCHECKED`의 세 가지 상태의 확인란 단추를 만듭니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지고 단추 상태가 변경됩니다.  단추 상태는 `BST_CHECKED`, `BST_INDETERMINATE` 및 `BST_UNCHECKED`의 순서로 순환합니다.  기본적으로, 관련 텍스트가 확인란 오른쪽에 표시됩니다.  확인란의 왼쪽에 텍스트를 표시하려면 사용하는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_AUTOCHECKBOX`|`BST_CHECKED`, `BST_UNCHECKED`의 두 가지 상태의 확인란 단추를 만듭니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지고 단추 상태가 변경됩니다.  기본적으로, 관련 텍스트가 확인란 오른쪽에 표시됩니다.  확인란의 왼쪽에 텍스트를 표시하려면 사용하는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_AUTORADIOBUTTON`|`BST_CHECKED`, `BST_UNCHECKED`의 두 가지 상태의 라디오 단추를 만듭니다.  라디오 단추는 일반적으로 그룹에 사용되며, 각 그룹에서는 한 번에 최대 한 개의 옵션만 선택할 수 있습니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지고 클릭한 라디오 단추의 상태가 `BST_CHECKED`로 설정되며 단추 그룹에 있는 다른 라디오 단추의 상태가 모두 `BST_UNCHECKED`로 설정됩니다.  기본적으로 관련 텍스트가 라디오 단추 오른쪽에 표시됩니다.  라디오 단추의 왼쪽에 텍스트를 표시하려면 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_CHECKBOX`|`BST_CHECKED`, `BST_UNCHECKED`의 두 가지 상태의 확인란 단추를 만듭니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지지만 단추 상태는 변경되지 않습니다.  기본적으로, 관련 텍스트가 확인란 오른쪽에 표시됩니다.  확인란의 왼쪽에 텍스트를 표시하려면 사용하는 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_COMMANDLINK`|명령 링크 단추를 만듭니다.  명령 링크 단추는 메인 텍스트 왼쪽에 녹색 화살표를 표시하고 메인 텍스트 아래 메모를 표시하는 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]에만 해당하는 명령 단추입니다.  [CButton::SetNote](../Topic/CButton::SetNote.md)를 사용하여 메모 텍스트를 설정할 수 있습니다.|  
|`BS_DEFCOMMANDLINK`|명령 링크 단추를 만듭니다.  명령 링크 단추는 메인 텍스트 왼쪽에 녹색 화살표를 표시하고 메인 텍스트 아래 메모를 표시하는 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]에만 해당하는 명령 단추입니다.  [CButton::SetNote](../Topic/CButton::SetNote.md)를 사용하여 메모 텍스트를 설정할 수 있습니다.  대화 상자에 단추가 있는 경우 Enter 키를 누르면 단추에 입력 포커스가 없어도 대화 상자에 `BN_CLICKED` 알림이 전송됩니다.|  
|`BS_DEFPUSHBUTTON`|두꺼운 검정 테두리가 있는 명령 단추를 만듭니다.  대화 상자에 단추가 있는 경우 Enter 키를 누르면 단추에 입력 포커스가 없어도 대화 상자에 `BN_CLICKED` 알림이 전송됩니다.|  
|`BS_DEFSPLITBUTTON`|분할 단추를 만듭니다.  분할 단추는 드롭다운 화살표 옆의 단추가 포함되어 있고 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]에만 해당하는 명령 단추입니다.  이 단추를 클릭하면 기본 명령이 실행됩니다.  드롭다운 화살표를 클릭하면 추가 명령이 있는 메뉴가 표시됩니다.  대화 상자에 분할 단추가 있는 경우 Enter 키를 누르면 단추에 입력 포커스가 없어도 대화 상자에 `BN_CLICKED` 알림이 전송됩니다.|  
|`BS_GROUPBOX`|다른 단추를 그룹화할 수 있는 사각형을 만듭니다.  이 스타일과 연관된 텍스트는 사각형의 왼쪽 위 모서리에 표시됩니다.|  
|`BS_OWNERDRAW`|소유자가 그린 단추를 만듭니다.  단추의 시각적 측면이 변경되면 프레임워크가 `DrawItem` 메서드를 호출합니다.  `CBitmapButton` 클래스를 사용할 경우 이 스타일을 반드시 설정해야 합니다.|  
|`BS_PUSHBUTTON`|사용자가 단추를 클릭하면 `BN_CLICKED` 알림을 소유자 창에 보내는 명령 단추를 만듭니다.|  
|`BS_RADIOBUTTON`|`BST_CHECKED`, `BST_UNCHECKED`의 두 가지 상태의 라디오 단추를 만듭니다.  라디오 단추는 일반적으로 그룹에 사용되며, 각 그룹에서는 한 번에 최대 한 개의 옵션만 선택할 수 있습니다.  단추를 클릭하면 `BN_CLICKED` 알림이 소유자 창에 보내지지만 그룹에 있는 단추의 상태가 자동으로 변경되지는 않습니다.  기본적으로 관련 텍스트가 라디오 단추 오른쪽에 표시됩니다.  라디오 단추의 왼쪽에 텍스트를 표시하려면 `BS_LEFTTEXT` 또는 `BS_RIGHTBUTTON` 스타일을 사용합니다.|  
|`BS_SPLITBUTTON`|분할 단추를 만듭니다.  분할 단추는 드롭다운 화살표 옆의 단추가 포함되어 있고 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]에만 해당하는 명령 단추입니다.  이 단추를 클릭하면 기본 명령이 실행됩니다.  드롭다운 화살표를 클릭하면 추가 명령이 있는 메뉴가 표시됩니다.|  
|`BS_USERBUTTON`|사용되지는 않지만, 16비트 버전 Windows와의 호환성을 위해 제공됩니다.  Win32 기반 응용 프로그램은 대신 `BS_OWNERDRAW`를 사용해야 합니다.|  
  
## 라디오 단추 및 확인란 스타일  
 다음 표에는 라디오 단추 및 확인란에만 적용되는 스타일이 나와 있습니다.  다른 형식의 단추에서는 이러한 스타일이 무시됩니다.  옵션으로 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|---------|--------|  
|`BS_LEFTTEXT`|라디오 단추나 확인란 스타일로 결합하면 라디오 단추나 확인란 왼쪽에 텍스트가 표시됩니다.|  
|`BS_RIGHTBUTTON`|라디오 단추나 확인란 스타일로 결합하면 라디오 단추나 확인란 왼쪽에 텍스트가 표시됩니다.  이 스타일은 `BS_LEFTTEXT` 스타일과 동일합니다.|  
|`BS_PUSHLIKE`|확인란 또는 라디오 단추가 명령 단추처럼 동작하도록 만듭니다.  `BST_CHECKED` 상태에 있을 때 버튼이 눌린 것으로 표시되며, `BST_INDETERMINATE` 상태에 있을 때는 흐리게 눌린 것으로 표시, `BST_UNCHECKED` 상태에 있을 때에는 해제된 것으로 표시됩니다.|  
  
## 텍스트 맞춤 스타일  
 다음 표에는 수평 및 수직 텍스트 맞춤 옵션이 나와 있습니다.  옵션으로 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|---------|--------|  
|`BS_LEFT`|단추 사각형에서 텍스트를 왼쪽에 맞춥니다.  그러나 단추가 `BS_RIGHTBUTTON` 스타일이 없는 확인란 또는 라디오 단추인 경우 텍스트는 확인란 또는 라디오 단추 오른쪽에 왼쪽 정렬됩니다.|  
|`BS_RIGHT`|단추 사각형에서 텍스트를 오른쪽에 맞춥니다.  그러나 단추가 `BS_RIGHTBUTTON` 스타일이 없는 확인란 또는 라디오 단추인 경우 텍스트는 확인란 또는 라디오 단추 오른쪽에 오른쪽 정렬됩니다.|  
|`BS_CENTER`|단추 사각형에서 텍스트를 가로 방향으로 가운데에 맞춥니다.|  
|`BS_TOP`|단추 사각형의 상단에 텍스트를 배치합니다.|  
|`BS_BOTTOM`|단추 사각형의 아래쪽에 텍스트를 배치합니다.|  
|`BS_VCENTER`|단추 사각형에서 텍스트를 세로 방향으로 가운데에 맞춥니다.|  
  
## 단추 내용 옵션  
 다음 표에는 단추에 표시할 내용을 나타내는 옵션이 나와 있습니다.  텍스트만 표시하는 단추 형식은 이러한 스타일을 무시합니다.  옵션으로 다음 중 하나를 선택할 수 있습니다.  
  
|스타일|설명|  
|---------|--------|  
|`BS_BITMAP`|비트맵을 표시하는 단추를 지정합니다.|  
|`BS_ICON`|아이콘을 표시하는 단추를 지정합니다.|  
|`BS_TEXT`|텍스트를 표시하는 단추를 지정합니다.|  
  
## 기타 옵션  
 다음 표는 모든 단추 형식에서 사용할 수 있는 추가 옵션을 나열합니다.  옵션으로 다음 중 하나 이상을 선택할 수 있습니다.  
  
|스타일|설명|  
|---------|--------|  
|`BS_FLAT`|단추를 2차원으로 지정하고 3차원 이미지를 만들기 위한 기본 음영을 사용해서 그려지지 않도록 지정합니다.|  
|`BS_MULTILINE`|텍스트 문자열이 너무 길어 단추 사각형에서 한 줄에 맞지 않을 경우 단추 텍스트를 여러 줄로 줄 바꿈합니다.|  
|`BS_NOTIFY`|부모 창에 `BN_DBLCLK`, `BN_KILLFOCUS` 및 `BN_SETFOCUS` 알림을 전송하려면 단추를 사용합니다.  단추는 이 스타일이 지정되었는지 여부와 상관없이 `BN_CLICKED` 알림을 전송합니다.|  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../Topic/CButton::Create.md)   
 [Button 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775951)   
 [BN\_CLICKED Notification](_win32_bn_clicked_notification)