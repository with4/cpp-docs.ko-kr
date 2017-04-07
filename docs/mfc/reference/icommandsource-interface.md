---
title: "ICommandSource 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f923a8a42327cb74ce9323f72aae90c7411da27c
ms.lasthandoff: 02/24/2017

---
# <a name="icommandsource-interface"></a>ICommandSource 인터페이스
사용자 정의 컨트롤에 명령 원본 개체에서 보낸 명령만 관리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|명령 원본 개체에 명령 처리기를 추가합니다.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|명령 원본 개체에 명령 처리기의 그룹을 추가합니다.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|명령 원본 개체에 사용자 인터페이스 명령 메시지 처리기의 그룹을 추가합니다.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|명령 원본 개체에는 사용자 인터페이스 명령 메시지 처리기를 추가합니다.|  
|[ICommandSource::PostCommand](#postcommand)|처리 하기를 기다리지 않고 메시지를 게시 합니다.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|명령 원본 개체에서 명령 처리기를 제거합니다.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|명령 원본 개체에서 명령 처리기의 그룹을 제거합니다.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기의 그룹을 제거합니다.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거합니다.|  
|[ICommandSource::SendCommand](#sendcommand)|메시지를 보내고 반환 하기 전에 처리 하기를 기다립니다.|  
  
### <a name="remarks"></a>주의  
 MFC 뷰에서 사용자 정의 컨트롤을 호스팅할 때 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md) 경로 명령 및 update 명령 UI 메시지를 사용자 정의 컨트롤에 기록 MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)를 처리할 수 있도록 합니다. 구현 하 여 [ICommandTarget 인터페이스](../../mfc/reference/icommandtarget-interface.md), 사용자 정의 컨트롤에 대 한 참조를 제공 된 `ICommandSource` 개체입니다.  
  
 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `ICommandTarget`합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
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
명령 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>주의
이 메서드는 명령 처리기 cmdHandler 명령 원본 개체에 추가 하 고 처리기 cmdID 매핑됩니다.
참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](https://msdn.microsoft.com/library/y33d8624.aspx) AddCommandHandler를 사용 하는 방법의 예입니다.

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

명령 원본 개체에 명령 처리기의 그룹을 추가합니다.
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
명령이 매핑되는 메시지 처리기 메서드에 대 한 핸들입니다.
### <a name="remarks"></a>주의
이 메서드는 단일 메시지 처리기를 명령 Id의 연속 된 범위에 매핑하 명령 원본 개체에 추가 합니다. 이 한 방법으로 관련 된 여러 단추 그룹을 처리 하기 위해 사용 됩니다.

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
명령 원본 개체에 사용자 인터페이스 명령 메시지 처리기의 그룹을 추가합니다.
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
명령이 매핑되는 메시지 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>주의
이 메서드는 단일 사용자 인터페이스 명령 메시지 처리기를 명령 Id의 연속 된 범위를 매핑합니다 명령 원본 개체에 추가 합니다. 이 한 방법으로 관련 된 여러 단추 그룹을 처리 하기 위해 사용 됩니다.

## <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler
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
사용자 인터페이스 명령 메시지 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>주의
이 메서드는 사용자 인터페이스 명령 메시지 처리기 cmdHandler 명령 원본 개체에 추가 하 고 처리기 cmdID 매핑됩니다.

## <a name="postcommand"></a>ICommandSource::PostCommand
처리 하기를 기다리지 않고 메시지를 게시 합니다.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>매개 변수
`command`  
게시할 메시지의 명령 ID입니다.
### <a name="remarks"></a>주의
이 메서드는 비동기적으로 명령에 의해 지정 된 ID에 매핑되는 메시지를 게시 합니다. 창의 메시지 큐에 메시지를 저장 하는 CWnd::PostMessage를 호출 하 고 해당 창 메시지를 처리할 때까지 기다리지 않고 반환 합니다.


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
명령 원본 개체에서 명령 처리기를 제거합니다.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>매개 변수
`cmdID`  
명령 ID입니다.
### <a name="remarks"></a>주의
이 메서드는 명령 원본 개체에서 cmdID에 매핑된 명령 처리기를 제거 합니다.


## <a name="removecommandrangecommandhandler"></a>ICommandSource::RemoveCommandRangeHandler 
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
### <a name="remarks"></a>주의
이 메서드는 메시지 처리기에 매핑된 명령 Id 지정 cmdIDMin 및 cmdIDMax, 명령 원본 개체에서 그룹을 제거 합니다.

## <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler 
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
### <a name="remarks"></a>주의
이 메서드는 사용자 인터페이스 명령 메시지 처리기에 매핑된 명령 Id 지정 cmdIDMin 및 cmdIDMax, 명령 원본 개체에서 그룹을 제거 합니다.

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거합니다.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>매개 변수
`cmdID`  
명령 ID입니다.
### <a name="remarks"></a>주의
이 메서드는 명령 원본 개체에서 cmdID에 매핑된 사용자 인터페이스 명령 메시지 처리기를 제거 합니다.

## <a name="sendcommand"></a>ICommandSource::SendCommand 
메시지를 보내고 반환 하기 전에 처리 하기를 기다립니다.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>매개 변수
`command`  
보낼 메시지의 명령 ID입니다.
### <a name="remarks"></a>주의
이 메서드는 동기적으로 명령에 의해 지정 된 ID에 매핑되는 메시지를 보냅니다. 창의 메시지 큐에 메시지를 저장 하는 CWnd::SendMessage를 호출 하 고 해당 창 프로시저에서 메시지를 반환 하기 전에 처리 될 때까지 기다립니다.
## <a name="see-also"></a>참고 항목  
 [방법: 추가 명령 라우팅 windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget 인터페이스](../../mfc/reference/icommandtarget-interface.md)

