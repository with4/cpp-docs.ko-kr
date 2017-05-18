---
title: "ICommandUI 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
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
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>ICommandUI 인터페이스
사용자 인터페이스 명령을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[icommandui__Check](#check)|이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.|  
|[ICommandUI::ContinueRouting](#continuerouting)|현재 메시지의 처리기는 체인을 계속 하려면 명령 라우팅 메커니즘에 알려줍니다.|  
|[ICommandUI::Enabled](#enabled)|이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[ICommandUI::ID](#id)|가 나타내는 사용자 인터페이스 개체의 ID를 가져옵니다는 `ICommandUI` 개체입니다.|  
|[ICommandUI::Index](#index)|가 나타내는 사용자 인터페이스 개체의 인덱스를 가져옵니다는 `ICommandUI` 개체입니다.|  
|[ICommandUI::Radio](#radio)|이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.|  
|[ICommandUI::Text](#text)|이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 사용자 인터페이스 명령을 관리 하는 메서드와 속성을 제공 합니다. `ICommandUI`유사한 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)점을 제외 하 고 `ICommandUI` .NET 구성 요소와 상호 운용 되는 MFC 응용 프로그램에 사용 됩니다.  
  
 `ICommandUI`내에서 사용 되는 `ON_UPDATE_COMMAND_UI` 의 처리기는 [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-클래스를 파생 합니다. 메뉴에서 각 메뉴 항목 사용으로 표시 됩니다 (선택 해야 하는지 또는) 응용 프로그램의 사용자를 활성화 하는 경우 또는 사용 하지 않도록 설정 합니다. 구현 하 여이 정보를 제공 하는 각 메뉴 명령에 대상은 `ON_UPDATE_COMMAND_UI` 처리기입니다. 각 응용 프로그램에서 명령 사용자 인터페이스 개체에 대 한 메시지-맵 항목 및 각 처리기에 대 한 함수 프로토타입을 만드는 속성 창을 사용 합니다.  
  
 방법에 대 한 자세한 내용은 `ICommandUI` 인터페이스는 명령 라우팅에 사용을 참조 하십시오. [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
 MFC의 사용자 인터페이스 명령을 관리 되는 방법에 대 한 자세한 내용은 참조 하십시오. [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)합니다.  
  
## <a name="check"></a>ICommandUI::Check  
이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.
```
property UICheckState Check;
```
## <a name="remarks"></a>주의  
이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 다음 값을 확인을 설정 합니다.  
- 0 선택 취소  
- 1  
- 비활성화 상태의 설정&2;  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
현재 메시지의 처리기는 체인을 계속 하는 명령 라우팅 메커니즘을 알려줍니다.
```
void ContinueRouting();
```
## <a name="remarks"></a>주의
FALSE를 반환 하는 ON_COMMAND_EX 처리기와 함께에서 사용 해야 하는 고급 멤버 함수입니다. 자세한 내용은 기술 참고 TN006 참조: 메시지 맵.

## <a name="enabled"></a>ICommandUI::Enabled 
이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 사용 합니다.
```
property bool Enabled;
```
## <a name="remarks"></a>주의
이 속성 사용 하거나이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 합니다. 사용 항목을 사용 하지 않도록 하려면 FALSE true로 설정 하는 Enabled를 설정 합니다.

## <a name="id"></a>ICommandUI::ID  
ICommandUI 개체로 표현 되는 사용자 인터페이스 개체의 ID를 가져옵니다.
```
property unsigned int ID;
```
## <a name="remarks"></a>주의
이 속성의 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체가 나타내는 다른 사용자 인터페이스 개체의 ID를 (핸들)를 가져옵니다.

## <a name="index"></a>ICommandUI::Index   
ICommandUI 개체로 표현 되는 사용자 인터페이스 개체의 인덱스를 가져옵니다.
```
property unsigned int Index;
```
## <a name="remarks"></a>주의
이 속성의 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체가 나타내는 다른 사용자 인터페이스 개체의 인덱스를 (핸들)를 가져옵니다.

## <a name="radio"></a>ICommandUI::Radio 
이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.
```
property bool Radio;
```
## <a name="remarks"></a>주의
이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 항목이 사용 하도록 설정 하려면 true이 고 라디오를 설정 그렇지 않으면 FALSE입니다.

## <a name="text"></a>ICommandUI::Text 
이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다.
```
property String^ Text;
```
## <a name="remarks"></a>주의
이 속성이이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 합니다. 텍스트 문자열 핸들에 텍스트를 설정 합니다.

## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  
  
## <a name="see-also"></a>참고 항목  
 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)

