---
title: "CWaitCursor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1cf5c850158e445e7695b85e540b1e0c162e621c
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="cwaitcursor-class"></a>CWaitCursor 클래스
사용자가 장기 작업을 수행하는 동안 대기 커서를 표시하는 한 가지 방법(일반적으로 모래시계로 표시됨)을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|생성 된 `CWaitCursor` 개체를 대기 커서를 표시 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|변경 된 후 대기 커서를 복원 합니다.|  
  
## <a name="remarks"></a>설명  
 `CWaitCursor`기본 클래스는 없습니다.  
  
 좋은 Windows 프로그래밍 방법 때마다 시간이 오래 걸리는 하는 작업을 수행 하는 대기 커서를 표시 해야 합니다.  
  
 대기 커서를 표시 하려면 정의 `CWaitCursor` 시간이 오래 걸리는 작업을 수행 하는 코드 하기 전에 변수입니다. 개체의 생성자 표시할 대기 커서를 자동으로 발생 합니다.  
  
 개체가 범위를 벗어날 때 (에 블록의 끝에는 `CWaitCursor` 개체를 선언), 소멸자 이전 커서에 커서를 설정 합니다. 즉, 개체는 필요한 정리 자동으로 수행합니다.  
  
> [!NOTE]
>  해당 생성자 및 소멸자의 작동 방식을 인해 `CWaitCursor` 개체는 항상 지역 변수로 선언-전역 변수로 선언 되지 나 사용 하 여 이러한 할당은 **새**합니다.  
  
 커서를 변경할 수는 메시지 상자 또는 대화 상자, 호출을 표시 하는 등을 일으킬 수 있는 작업을 수행 하는 경우는 [복원](#restore) 대기 커서를 복원 하는 멤버 함수입니다. 호출할 수 **복원** 도 때 대기 커서를 현재 표시 되어 있습니다.  
  
 조합을 사용 하는 대기 커서를 표시 하는 다른 방법은 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), 용도나 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). 그러나 `CWaitCursor` 시간이 오래 걸리는 작업을 완료 되 면 이전 커서에 커서를 설정 하려면 필요가 없기 때문에 사용 하기 쉽습니다.  
  
> [!NOTE]
>  설정 하 고 사용 하 여 커서를 복원 하는 MFC는 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) 가상 함수입니다. 사용자 지정 동작을 제공 하려면이 함수를 재정의할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CWaitCursor`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
## <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 대기 커서를 표시 하려면 선언는 `CWaitCursor` 시간이 오래 걸리는 작업을 수행 하는 코드 앞에 개체입니다.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>설명  
 생성자 표시할 대기 커서를 자동으로 발생 합니다.  
  
 개체가 범위를 벗어날 때 (에 블록의 끝에는 `CWaitCursor` 개체를 선언), 소멸자 이전 커서에 커서를 설정 합니다. 즉, 개체는 필요한 정리 자동으로 수행합니다.  
  
 부분 함수에만 대기 커서를 활성화 하려면 (이 문서의 함수 종료 전에) 블록의 끝에 소멸자가 호출 사실을 이용할 수 있습니다. 이 기술은 아래의 두 번째 예제에 표시 됩니다.  
  
> [!NOTE]
>  해당 생성자 및 소멸자의 작동 방식을 인해 `CWaitCursor` 개체는 항상 지역 변수로 선언-전역 변수로 선언 되지 나 사용 하 여 이러한 할당은 **새**합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 대기 커서를 복원 하려면 메시지 상자 또는 다른 커서에 대기 커서를 변경 될 수 있는 대화 상자를 표시 하는 등의 작업을 수행한 후이 함수를 호출 합니다.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>설명  
 호출을 **복원** 도 대기 커서가 표시 되 면 현재 합니다.  
  
 에 있는 것 이외의 다른 함수에 있는 동안 대기 커서를 복원 해야 하는 경우는 `CWaitCursor` 호출할 수 있습니다, 개체를 선언 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [할까요?: Microsoft Foundation 클래스 응용 프로그램 단위로 나타낸 마우스 포인터를 어떻게 변경 됩니까](http://go.microsoft.com/fwlink/p/?linkid=128044)



