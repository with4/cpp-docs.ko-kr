---
title: CSimpleDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a8f6cb2ead8798b86d65a1fa875a42a68cdd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="csimpledialog-class"></a>CSimpleDialog 클래스
이 클래스는 기본 모달 대화 상자를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>매개 변수  
 *t_wDlgTemplateID*  
  
 대화 상자 템플릿 리소스의 리소스 ID입니다.  
  
 *t_bCenter*  
 **True 이면** 소유자 창에서 가운데에 맞출지 필요가 없으면이 대화 상자 개체 **FALSE**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|모달 대화 상자를 만듭니다.|  
  
## <a name="remarks"></a>설명  
 기본 기능으로 모달 대화 상자를 구현 합니다. `CSimpleDialog` Windows 공용 컨트롤만 지원을 합니다. 을 만들고 모달 대화 상자를 표시 하려면 대화 상자에 대 한 기존 리소스 템플릿 이름을 제공 하는이 클래스의 인스턴스를 만듭니다. 대화 상자 개체 (예: IDOK 또는 IDCANCEL) 미리 정의 된 값을 가진 모든 컨트롤을 마우스 오른쪽 단추로 클릭할 때 닫힙니다.  
  
 `CSimpleDialog` 모달 대화 상자만 만들 수 있습니다. `CSimpleDialog` 기본 메시지 맵을 메시지를 적절 한 처리기를 사용 하 여 대화 상자 프로시저를 제공 합니다.  
  
 참조 [대화 상자를 구현](../../atl/implementing-a-dialog-box.md) 자세한 정보에 대 한 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="domodal"></a>  CSimpleDialog::DoModal  
 모달 대화 상자를 호출 하 고 완료 한 후 대화 상자 결과 반환 합니다.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 대화 상자의 부모에 대 한 핸들입니다. 값이 제공 하는 경우 부모는 현재 활성 창으로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 반환 값은 대화 상자를 해제 하는 컨트롤의 리소스 ID입니다.  
  
 함수가 실패 하면 반환 값은-1입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 대화 상자가 활성화 되어 있는 동안 사용자와 모든 상호 작용을 처리 합니다. 이 대화 상자 모달; 사용 즉, 사용자는 대화 상자를 닫을 때까지 다른 창 상호 작용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
