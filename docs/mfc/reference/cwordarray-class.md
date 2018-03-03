---
title: "CWordArray 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5804df97c54a111a02b79dc849c20c91ba8176b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cwordarray-class"></a>CWordArray 클래스
16비트 단어 배열을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>멤버  
 멤버 함수 `CWordArray` 클래스의 멤버 함수와 비슷한 [CObArray](../../mfc/reference/cobarray-class.md)합니다. 이처럼 두 함수가 비슷하므로 `CObArray` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. 볼 때마다는 [CObject](../../mfc/reference/cobject-class.md) 포인터를 함수 매개 변수 또는 반환 값으로 대체 한 **단어**합니다.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 예를 들어 위의 코드는  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|빈 배열을 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|지정된 인덱스의 값을 반환합니다.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|배열의 요소에 대한 액세스를 허용합니다. 수 **NULL**합니다.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|유효한 최대 인덱스를 반환합니다.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|배열이 비어 있는지를 확인합니다.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|이 배열의 모든 요소를 반환합니다.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|특정 인덱스의 요소를 제거합니다.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CObArray::operator &#91; &#93;](../../mfc/reference/cobarray-class.md#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 `CWordArray`통합 된 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 serialization 및 요소 덤프를 지원 합니다. 단어의 배열을 오버 로드 된 삽입 연산자 또는으로 보관 파일로 저장 되는 경우는 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 멤버 함수의 경우 각 요소가 이면 차례로 직렬화 합니다.  
  
> [!NOTE]
>  배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.  
  
 배열에 있는 개별 요소의 덤프가 필요한 경우 덤프 컨텍스트 깊이 1 이상으로 설정 해야 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CWordArray`, 문서를 참조 [컬렉션](../../mfc/collections.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>ICommandSource 인터페이스  
 사용자 정의 컨트롤에 명령 원본 개체에서 전송 되는 명령을 관리 합니다.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>설명  
 MFC 뷰에서 사용자 정의 컨트롤을 호스팅하는 경우 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md) 경로 명령 및 업데이트 명령을 MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 허용 하는 사용자 정의 컨트롤에 UI 메시지입니다. 를 구현 하면 사용자 정의 컨트롤에 대 한 참조는 `ICommandSource` 개체입니다.  
  
 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `ICommandTarget`합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 명령 원본 개체에 명령 처리기를 추가합니다.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
  
 `cmdHandler`  
 명령 처리기 메서드인에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 명령 처리기를 추가 `cmdHandler` 명령 원본 개체에 매핑되는 처리기에 `cmdID`합니다.  
  
 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `AddCommandHandler`합니다.  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 명령 원본 개체에 명령 처리기의 그룹을 추가 합니다.  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdIDMin`  
 명령 ID 범위의 시작 인덱스입니다.  
  
 `cmdIDMax`  
 명령 ID 범위의 끝 인덱스입니다.  
  
 `cmdHandler`  
 명령이 매핑되는 메시지 처리기 방법에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 명령 Id의 연속 된 범위 단일 메시지 처리기에 매핑하고 명령 원본 개체에 추가 합니다. 이 한 방법으로 관련 된 단추 그룹을 처리 하기 위한 사용 됩니다.  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 명령 원본 개체에 사용자 인터페이스 명령 메시지 처리기의 그룹을 추가 합니다.  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdIDMin`  
 명령 ID 범위의 시작 인덱스입니다.  
  
 `cmdIDMax`  
 명령 ID 범위의 끝 인덱스입니다.  
  
 `cmdHandler`  
 명령이 매핑되는 메시지 처리기 방법에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 단일 사용자 인터페이스 명령 메시지 처리기를 명령 Id의 연속 된 범위를 매핑하고 명령 원본 개체에 추가 합니다. 이 한 방법으로 관련 된 단추 그룹을 처리 하기 위한 사용 됩니다.  
  
##  <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
 명령 원본 개체에는 사용자 인터페이스 명령 메시지 처리기를 추가합니다.  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
  
 `cmdUIHandler`  
 사용자 인터페이스 명령 메시지 처리기 방법에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자 인터페이스 명령 메시지 처리기 추가 `cmdHandler` 명령 원본 개체에 매핑되는 처리기에 `cmdID`합니다.  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 처리 되기를 기다리지 않고 메시지를 게시 합니다.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>매개 변수  
 `command`  
 게시 될 메시지의 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 비동기적으로 하 여 지정 된 ID에 매핑된 메시지 게시 `command`합니다. 호출 [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) 해당 창 메시지를 처리할 때까지 기다리지 않고 창의 메시지 큐와 돌아올에 메시지를 배치할 수 있습니다.  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 명령 원본 개체에서 명령 처리기를 제거합니다.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 매핑할 명령 처리기를 제거 `cmdID` 명령 소스 개체에서입니다.  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 명령 원본 개체에서 명령 처리기의 그룹을 제거합니다.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdIDMin`  
 명령 ID 범위의 시작 인덱스입니다.  
  
 `cmdIDMax`  
 명령 ID 범위의 끝 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 메시지 처리기에서 명령 Id 지정에 매핑된의 그룹을 제거 `cmdIDMin` 및 `cmdIDMax`, 명령 원본 개체에서 합니다.  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기의 그룹을 제거합니다.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdIDMin`  
 명령 ID 범위의 시작 인덱스입니다.  
  
 `cmdIDMax`  
 명령 ID 범위의 끝 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자 인터페이스 명령 메시지 처리기를에서 명령 Id 지정에 매핑된의 그룹을 제거 `cmdIDMin` 및 `cmdIDMax`, 명령 원본 개체에서 합니다.  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거합니다.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdID`  
 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는에 매핑된 사용자 인터페이스 명령 메시지 처리기를 제거 `cmdID` 명령 소스 개체에서입니다.  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 메시지를 보내고 반환 하기 전에 처리 되기를 기다립니다.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>매개 변수  
 `command`  
 보낼 메시지의 명령 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 동기적으로 처리 하 여 지정 된 ID에 매핑된 메시지 전송 `command`합니다. 호출 [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 해당 창 프로시저에서 반환 하기 전에 메시지를 처리할 때 까지는 창의 메시지 큐와 대기에 메시지를 배치 합니다.  
  
##  <a name="icommandtarget_interface"></a>ICommandTarget 인터페이스  
 명령 원본 개체에서 명령을 수신 하도록 인터페이스와 함께 사용자 정의 컨트롤을 제공 합니다.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>설명  
 MFC 뷰에서 사용자 정의 컨트롤을 호스팅하는 경우 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 경로 명령 및 업데이트 명령을 MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 허용 하는 사용자 정의 컨트롤에 UI 메시지입니다. 구현 하 여 `ICommandTarget`, 사용자 정의 컨트롤 개체에 대 한 참조를 제공 합니다.  
  
 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `ICommandTarget`합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 명령 대상 개체를 초기화합니다.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdSource`  
 명령 원본 개체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 MFC 뷰에서 사용자 정의 컨트롤을 호스팅하는 경우 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 경로 명령 및 업데이트 명령을 MFC 명령을 처리할 수 있도록 허용 하는 사용자 정의 컨트롤에 UI 메시지입니다.  
  
 이 메서드는 명령 대상 개체를 초기화 하 고 지정 된 명령 원본 개체와 연결 `cmdSource`합니다. 사용자 컨트롤 클래스 구현에서 호출 되어야 합니다. 초기화 하는 과정을 등록 해야 명령 처리기 명령 원본 개체와 호출 하 여 [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) 에 `Initialize` 구현 합니다. 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `Initialize` 에이 작업을 수행 합니다.  
  
##  <a name="icommandui_interface"></a>ICommandUI 인터페이스  
 사용자 인터페이스 명령을 관리합니다.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>설명  
 이 인터페이스는 메서드 및 사용자 인터페이스 명령을 관리 하는 속성을 제공 합니다. `ICommandUI`유사한 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)제외 하 고 `ICommandUI` .NET 구성 요소와 상호 운용 하는 MFC 응용 프로그램에 사용 됩니다.  
  
 `ICommandUI`내에서 사용 되는 `ON_UPDATE_COMMAND_UI` 처리기-파생된 클래스에서 합니다. 메뉴에서 각 메뉴 항목으로 사용 하도록 설정 표시 됩니다 (선택 해야 하는지 또는) 응용 프로그램의 사용자를 활성화 하는 경우 또는 사용 하지 않도록 설정 합니다. 구현 하 여이 정보를 제공 하는 각 메뉴 명령 대상일은 `ON_UPDATE_COMMAND_UI` 처리기입니다. 각 응용 프로그램의 명령 사용자 인터페이스 개체에 대 한 속성 창을 사용 메시지-맵 항목 및 각 처리기에 대 한 함수 프로토타입을 만들 수 있습니다.  
  
 방법에 대 한 자세한 내용은 `ICommandUI` 인터페이스는 명령 라우팅에 사용을 참조 하십시오. [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
 MFC의 사용자 인터페이스 명령 관리 되는 방법에 대 한 자세한 내용은 참조 하십시오. [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)합니다.  
  
##  <a name="check"></a>ICommandUI::Check  
 이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>설명  
 이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 설정 `Check` 다음과 같은 값으로.  
  
|용어|정의|  
|----------|----------------|  
|0|선택 취소|  
|1|확인|  
|2|비활성화 상태 설정|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 현재 메시지 처리기의 체인을 라우팅 계속 하려면는 명령 라우팅 메커니즘을 알려줍니다.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>설명  
 와 함께에서 사용 해야 하는 고급 멤버 함수는 [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) 반환 하는 처리기 `FALSE`합니다. 자세한 내용은 기술 참고를 참조 하십시오. [TN006: 메시지 맵](../../mfc/tn006-message-maps.md)합니다.  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>설명  
 이 속성 사용 하거나이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 합니다. 설정 `Enabled` 를 `TRUE` 해당 항목을 사용할 수 있도록 `FALSE` 사용 하지 않도록 합니다.  
  
##  <a name="id"></a>ICommandUI::ID  
 가 나타내는 사용자 인터페이스 개체의 ID를 가져옵니다는 `ICommandUI` 개체입니다.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>설명  
 이 속성을 가져옵니다 도구 모음 단추, 메뉴 항목의 ID (핸들) 또는 기타 사용자 인터페이스 개체를 나타내는 `ICommandUI` 개체입니다.  
  
##  <a name="index"></a>ICommandUI::Index  
 가 나타내는 사용자 인터페이스 개체의 인덱스를 가져옵니다는 `ICommandUI` 개체입니다.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>설명  
 이 속성을 가져옵니다 도구 모음 단추, 메뉴 항목의 인덱스 (핸들) 또는 기타 사용자 인터페이스 개체를 나타내는 `ICommandUI` 개체입니다.  
  
##  <a name="radio"></a>ICommandUI::Radio  
 이 명령에 대 한 사용자 인터페이스 항목을 적절 한 선택 상태를 설정합니다.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>설명  
 이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 설정 `Radio` 를 `TRUE` ; 항목을 설정 하려면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="text"></a>ICommandUI::Text  
 이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 합니다.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>설명  
 이 속성을이 명령에 대 한 사용자 인터페이스 항목의 설정입니다. 설정 `Text` 텍스트 문자열 핸들에 있습니다.  
  
##  <a name="iview_interface"></a>IView 인터페이스  
 몇 가지 메서드를 구현 하는 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 를 사용 하는 관리 되는 컨트롤에 알림을 보냅니다.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>설명  
 `IView`몇 가지 메서드를 구현 하는 `CWinFormsView` 호스팅된 관리 되는 컨트롤에 공통 보기 알림을 전달할를 사용 하 여 합니다. 이들은 [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) 및 [OnActivateView](../../mfc/reference/iview-interface.md)합니다.  
  
 `IView`유사한 [CView](../../mfc/reference/cview-class.md), 하지만 관리 되는 보기 및 컨트롤에만 사용 됩니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 뷰 활성화 또는 비활성화 하는 경우에 MFC에서 호출 됩니다.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>매개 변수  
 `activate`  
 보기를 새로 있는지 여부를 나타냅니다. 활성화 또는 비활성화 합니다.  
  
##  <a name="oninitialupdate"></a>IView::OnInitialUpdate  
 보기에는 문서에 처음 연결 되었으나 처음 표시 되는 보기 프레임 워크에서 호출 됩니다.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 문서 보기의 수정 된 후에 MFC에서 호출 됩니다.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>설명  
 이 함수에서는 보기 수정 내용을 반영 하도록 표시를 업데이트 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 수집](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



