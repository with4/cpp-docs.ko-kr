---
title: "CSimpleDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleDialog
- CSimpleDialgo
- CSimpleDialog
- ATL.CSimpleDialog
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a4c17a1da8d1be00ebff171af09bc6c8eb81ed44
ms.lasthandoff: 02/24/2017

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
 **True 이면** 경우 대화 상자 개체 소유자 창에 집중 하 고, 그렇지 않으면를 **FALSE**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|모달 대화 상자를 만듭니다.|  
  
## <a name="remarks"></a>주의  
 기본 기능만 갖춘 모달 대화 상자를 구현합니다. `CSimpleDialog`Windows 공용 컨트롤만을 위한 지원을 제공합니다. 을 만들고 모달 대화 상자를 표시 하려면 대화 상자에 기존 리소스 템플릿의 이름을 제공 하는이 클래스의 인스턴스를 만듭니다. 대화 상자 개체 (예: IDOK 또는 IDCANCEL) 미리 정의 된 값을 가진 모든 컨트롤을 마우스 오른쪽 단추로 클릭할 때 닫힙니다.  
  
 `CSimpleDialog`모달 대화 상자만 만들 수 있습니다. `CSimpleDialog`적절 한 처리기에 메시지를 직접 기본 메시지 맵을 사용 하 여 대화 상자 절차를 제공 합니다.  
  
 참조 [대화 상자 구현](../../atl/implementing-a-dialog-box.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="a-namedomodala--csimpledialogdomodal"></a><a name="domodal"></a>CSimpleDialog::DoModal  
 모달 대화 상자를 호출 하 고 끝나면 대화 상자 결과 반환 합니다.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 대화 상자의 부모에 대 한 핸들입니다. 없는 값을 제공 하는 경우 부모는 현재 활성 창에 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 반환 값은 대화 상자를 해제 하는 컨트롤의 리소스 ID로 설정 합니다.  
  
 함수가 실패 한 경우 반환 값은-1입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 대화 상자가 활성화 되는 동안 모든 사용자 상호 작용을 처리 합니다. 이 사용 하 여 대화 상자 모달; 즉, 사용자 대화 상자를 닫을 때까지 다른 창을 사용할 수는 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

