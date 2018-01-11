---
title: "CDaoRecordView 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
dev_langs: C++
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2fffeed33d5b966faf511f60da740c39f2b91581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaorecordview-class"></a>CDaoRecordView 클래스
컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|`CDaoRecordView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|현재 레코드 관련된 레코드 집합의 첫 번째 레코드는 0이 아닌 반환 합니다.|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|현재 레코드 관련된 레코드 집합의 마지막 레코드 이면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|파생 된 클래스의 개체에 대 한 포인터를 반환 `CDaoRecordset`합니다. Classwizard 함께 사용 하면에 대 한이 함수를 재정의 하 고 필요한 경우 레코드 집합을 만듭니다.|  
|[CDaoRecordView::OnMove](#onmove)|현재 레코드가 변경 된 경우 데이터 원본에서 업데이트 한 다음 지정 된 레코드로 이동 (다음, 이전, 첫 번째 또는 마지막).|  
  
## <a name="remarks"></a>설명  
 뷰는에 직접 연결 하는 폼 보기는 `CDaoRecordset` 개체입니다. 뷰는 대화 상자 템플릿 리소스에서 만들어지고 필드가 표시 됩니다는 `CDaoRecordset` 대화 상자 템플릿에 컨트롤에는 개체입니다. `CDaoRecordView` 개체 (DDX) 대화 상자 데이터 교환 및 DAO 레코드 필드 교환 (DFX) 레코드 집합의 필드와 폼에서 컨트롤 간의 데이터 이동을 자동화를 사용 합니다. `CDaoRecordView`또한 이동 하는 기본 구현을 제공 하면 첫 번째 다음, 이전 또는 마지막 레코드와 보기에서 현재 레코드를 업데이트 하기 위한 인터페이스입니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 ODBC Open Database Connectivity ()를 기반으로 하는 MFC 데이터베이스 클래스와 다릅니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. 여전히 DAO 클래스; ODBC 데이터 원본에 액세스할 수 있습니다. DAO 클래스 Microsoft Jet 데이터베이스 엔진을 사용 하기 때문에 일반적으로 뛰어난 기능을 제공 합니다.  
  
 레코드 뷰를 만드는 가장 일반적인 방법은 응용 프로그램 마법사로입니다. 응용 프로그램 마법사에 레코드 뷰 클래스와 기본 시작 응용 프로그램의 일부로 관련된 레코드 집합 클래스를 모두 만듭니다.  
  
 단일 형식 하기만 하면, 응용 프로그램 마법사 접근 방식을 쉽습니다. 클래스 마법사를 사용 하면 개발 프로세스의 뒷부분에 나오는 레코드 뷰를 사용 하기로 수 있습니다. 레코드 뷰 클래스 만들지 않으면 응용 프로그램 마법사로 클래스 마법사와 나중에 만들 수 있습니다. 가장 융통성이 높은 방법은 클래스 마법사를 사용 하 여 레코드 뷰 및 레코드 집합을 별도로 만들 한 다음 해당 연결 레코드 집합 클래스 이름 지정 시에 더 많은 제어 제공 하므로 및 해당 합니다. H / 합니다. CPP 파일입니다. 이 방법에서는 동일한 레코드 집합 클래스에 여러 레코드 뷰를 포함할 수도 있습니다.  
  
 레코드 보기에서 레코드를 이동 하려면 최종 사용자가 쉽게 응용 프로그램 마법사 메뉴 (및 필요에 따라 도구 모음)을 만듭니다 리소스 이동은 첫 번째 다음, 이전 또는 마지막 레코드입니다. 클래스 마법사와 레코드 뷰 클래스를 만드는 경우 이러한 리소스를 직접 만들어야 하는 메뉴와 비트맵 편집기 해야 합니다.  
  
 레코드 간을 이동 하기 위한 기본 구현에 대 한 정보를 참조 하십시오. `IsOnFirstRecord` 및 `IsOnLastRecord` 및 문서 [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md), 둘 다에 적용 되는 `CRecordView` 및 `CDaoRecordView`합니다.  
  
 `CDaoRecordView`추적 레코드 집합에서 사용자의 위치 레코드 뷰 사용자 인터페이스를 업데이트할 수 있도록 합니다. 레코드 뷰 사용자 인터페이스 개체는 사용자가 레코드 집합의 한쪽 끝을 이동 하는 경우 비활성화-예: 메뉴 항목 또는 도구 모음 단추-이동 하기 위한 같은 방향으로 추가 합니다.  
  
 선언 및 레코드 뷰 및 레코드 집합 클래스를 사용 하는 방법에 대 한 자세한 내용은 문서에 "디자인 및 만들기 레코드" 뷰를 참조 [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다. 레코드 작업을 보는 방법 및 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md)합니다. 둘 다에 위에서 언급 한 모든 아티클에 적용 `CRecordView` 및 `CDaoRecordView`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="cdaorecordview"></a>CDaoRecordView::CDaoRecordView  
 파생 된 형식의 개체를 만들 때 `CDaoRecordView`, view 개체를 초기화 하 고 뷰의 기준이 되는 대화 상자 리소스를 식별 하는 생성자의 유형 중 하나를 호출 합니다.  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTemplateName`  
 대화 상자 템플릿 리소스의 이름에 해당 하는 null로 끝나는 문자열을 포함 합니다.  
  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID 번호를 포함합니다.  
  
### <a name="remarks"></a>설명  
 하거나 (인수에 문자열을 생성자에 전달) 이름 또는 ID (부호 없는 정수를 인수로 전달)가 리소스를 식별할 수 있습니다. 리소스를 사용 하 여 ID 것이 좋습니다.  
  
> [!NOTE]
>  파생된 클래스의 자체 생성자를 제공 해야 합니다. 파생된 클래스의 생성자에서 생성자를 호출 `CDaoRecordView::CDaoRecordView` 리소스 이름 또는 ID를 인수로 사용 합니다.  
  
 **CDaoRecordView::OnInitialUpdate** 호출 `CWnd::UpdateData`, 되는 호출 `CWnd::DoDataExchange`합니다. 이 초기 호출으로 `DoDataExchange` 연결 `CDaoRecordView` (간접적으로) 제어 `CDaoRecordset` 필드 classwizard 함께 사용 하 여 만든 데이터 멤버입니다. 기본 클래스를 호출 하 고 나면 될 때까지 이러한 데이터 멤버를 사용할 수 없습니다 **CFormView::OnInitialUpdate** 멤버 함수입니다.  
  
> [!NOTE]
>  마법사를 정의 하는 클래스 마법사를 사용 하는 경우는 `enum` 값 `CDaoRecordView::IDD` 클래스 선언 및 사용 하 여 목록에서 멤버 초기화는 생성자에 대 한 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>CDaoRecordView::IsOnFirstRecord  
 이 레코드 보기와 관련 된 레코드 집합 개체의 첫 번째 레코드는 현재 레코드 인지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>반환 값  
 현재 레코드는 레코드 집합;의 첫 번째 레코드 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 기본값의 자체 구현을 classwizard 함께 사용 하 여 작성 된 명령 업데이트 처리기를 작성할 때 유용 합니다.  
  
 사용자가 첫 번째 레코드를 이동 하면 모든 사용자 인터페이스 개체 (예: 메뉴 항목 또는 도구 모음 단추) 프레임 워크 비활성화 해야 이동 하는 첫 번째 또는 이전 레코드.  
  
##  <a name="isonlastrecord"></a>CDaoRecordView::IsOnLastRecord  
 이 레코드 보기와 관련 된 레코드 집합 개체의 마지막 레코드 현재 레코드 인지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>반환 값  
 현재 레코드는 레코드 집합;에 있는 마지막 레코드 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 기본값의 자체 구현을 클래스 마법사가 레코드 간을 이동 하기 위한 사용자 인터페이스를 지원 하기 위해 작성 하는 명령 업데이트 처리기를 작성할 때 유용 합니다.  
  
> [!CAUTION]
>  이 함수의 결과 신뢰할 수 있는 점을 제외 하 고 보기를 사용자가 것을 지 나 이동 될 때까지 레코드 집합의 끝을 검색할 수 수 있습니다. 사용자 레코드 뷰를 다음 또는 마지막 레코드로 이동에 대 한 모든 사용자 인터페이스 개체를 해제 해야 알 수 전에 마지막 레코드를 벗어나는 이동 해야 할 수 있습니다. 사용자 마지막 레코드를 지나서 이동 하 고 다시 마지막 레코드로 이동 하는 경우 (또는 앞), 레코드 뷰 수 레코드 집합에서 사용자의 위치를 추적 하 고 사용자 인터페이스 개체를 올바르게 사용 하지 않도록 설정 합니다.  
  
##  <a name="ongetrecordset"></a>CDaoRecordView::OnGetRecordset  
 에 대 한 포인터를 반환 합니다.는 `CDaoRecordset`-레코드 보기와 연결 된 개체를 파생 합니다.  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CDaoRecordset`-파생 개체 했으면 성공적으로 생성 된 개체는 **NULL** 포인터입니다.  
  
### <a name="remarks"></a>설명  
 생성 또는 레코드 집합 개체를 가져올 하 고에 대 한 포인터를 반환 하려면이 멤버 함수를 재정의 해야 합니다. 클래스 마법사로 레코드 뷰 클래스를 선언 하는 경우 마법사는 기본 재정의를 작성 합니다. 클래스 마법사의 기본 구현은 있을 경우 레코드 뷰에 저장 된 레코드 포인터를 반환 합니다. 클래스 마법사 및 호출을 사용 하 여 지정한 형식의 레코드 집합 개체를 생성 그렇지 않은 경우 해당 **열고** 멤버 함수를 테이블 열 또는 쿼리를 실행 한 다음 개체에 대 한 포인터를 반환 합니다.  
  
 자세한 내용 및 예제에 대 한 문서를 참조 [레코드 뷰: 레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md)합니다.  
  
##  <a name="onmove"></a>CDaoRecordView::OnMove  
 레코드 집합의 다른 레코드로 이동 하 고 레코드 뷰 컨트롤에서 해당 필드를 표시 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDMoveCommand`  
 표준 명령 ID 값이 다음 중 하나입니다.  
  
- `ID_RECORD_FIRST`레코드 집합의 첫 번째 레코드로 이동 합니다.  
  
- `ID_RECORD_LAST`레코드는 레코드 집합에서 마지막으로 이동 합니다.  
  
- `ID_RECORD_NEXT`레코드 집합의 다음 레코드로 이동 합니다.  
  
- `ID_RECORD_PREV`레코드 집합의 이전 레코드로 이동 합니다.  
  
### <a name="return-value"></a>반환 값  
 이동에 성공 하면 0이 아닌 그렇지 않은 경우 0 이동 요청이 거부 되었습니다.  
  
### <a name="remarks"></a>설명  
 적절 한 이동 멤버 함수를 호출 하는 기본 구현에서 `CDaoRecordset` 레코드 보기와 연결 된 개체입니다.  
  
 기본적으로 `OnMove` 사용자 레코드 보기에서 변경 된 경우 데이터 소스에서 현재 레코드를 업데이트 합니다.  
  
 응용 프로그램 마법사는 첫 번째 레코드, 마지막 레코드, 다음 레코드 및 이전 레코드 메뉴 항목과 함께 메뉴 리소스를 만듭니다. 초기 도구 모음 옵션을 선택 하는 경우 응용 프로그램 마법사 이러한 명령에 해당 하는 단추가 있는 도구 모음을 만듭니다.  
  
 레코드 집합의 마지막 레코드를 지 나 이동 하는 경우 레코드 뷰 계속 마지막 레코드를 표시 됩니다. 첫 번째 레코드를 지 나 뒤로 이동 하는 경우 첫 번째 레코드를 표시 하는 레코드 뷰 계속 합니다.  
  
> [!CAUTION]
>  호출 `OnMove` 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 적절 한 사용자 인터페이스 업데이트 처리기 함수를 호출- **OnUpdateRecordFirst**, **OnUpdateRecordLast**, **OnUpdateRecordNext**, 또는  **OnUpdateRecordPrev** -전에 해당 레코드 집합에 레코드가 있는지 확인 하는 작업으로 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFormView 클래스](../../mfc/reference/cformview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView 클래스](../../mfc/reference/cformview-class.md)
