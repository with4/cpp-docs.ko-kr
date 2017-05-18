---
title: "ICommandTarget 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 27
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 825fde18c56afb91bdb469212817109dc35abf68
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="icommandtarget-interface"></a>ICommandTarget 인터페이스
명령 원본 개체에서 명령을 수신 하도록 인터페이스와 함께 사용자 정의 컨트롤을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#initialize)|명령 대상 개체를 초기화합니다.|  
  
## <a name="remarks"></a>주의  
 MFC 뷰에서 사용자 정의 컨트롤을 호스팅할 때 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 경로 명령 및 update 명령 UI 메시지를 사용자 정의 컨트롤에 기록 MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)를 처리할 수 있도록 합니다. 구현 하 여 `ICommandTarget`, 사용자 정의 컨트롤에 대 한 참조를 제공 된 [ICommandSource](../../mfc/reference/icommandsource-interface.md) 개체입니다.  
  
 참조 [하는 방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `ICommandTarget`합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 명령 대상 개체를 초기화합니다.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>매개 변수  
 `cmdSource`  
 명령 원본 개체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 MFC 뷰로에서 사용자 정의 컨트롤을 호스팅할 때 cwinformsview 명령 및 update 명령 UI 메시지를 사용자 컨트롤에 MFC 명령을 처리할 수 있도록 합니다.  
  
 이 메서드 명령 대상 개체를 초기화 하 고 지정 된 명령 원본 개체 cmdSource와 연결 합니다. 사용자 컨트롤 클래스 구현에서 호출 되어야 합니다. 초기화 시 Initialize 구현에서 ICommandSource::AddCommandHandler 호출 하 여 명령 원본 개체에 명령 처리기를 등록 해야 합니다. 참조 하는 방법: 초기화를 사용 하 여이 작업을 수행 하는 방법의 예에 대 한 Windows Forms 컨트롤에 명령 라우팅 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 추가 명령 라우팅 windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource 인터페이스](../../mfc/reference/icommandsource-interface.md)




