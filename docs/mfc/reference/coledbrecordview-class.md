---
title: "COleDBRecordView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89b5cb175900d11854dcad03440a1ef0bfb8cff9
ms.lasthandoff: 02/24/2017

---
# <a name="coledbrecordview-class"></a>COleDBRecordView 클래스
컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|`COleDBRecordView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|표준 반환 `HRESULT` 값입니다.|  
|[COleDBRecordView::OnMove](#onmove)|데이터 원본에 대해 (더티) 경우 현재 레코드를 업데이트 하 고 다음 지정된 된 레코드를 이동 합니다 (다음, 이전, 첫 번째 또는 마지막).|  
  
## <a name="remarks"></a>주의  
 뷰는에 직접 연결 하는 폼 보기는 `CRowset` 개체입니다. 뷰는 대화 상자 템플릿 리소스에서 만들어지고의 필드를 표시 하는 `CRowset` 대화 상자 템플릿의 컨트롤에 개체입니다. `COleDBRecordView` 개체가 사용 하는 대화 상자 데이터 교환 (DDX) 및 탐색 기능에 기본 제공 `CRowset`, 폼에 컨트롤 및 행 집합의 필드 간의 데이터 이동을 자동화를 합니다. `COleDBRecordView`또한 이동에 대 한 기본 구현을 제공 하 고 첫 다음, 이전 또는 마지막 레코드와 보기에 현재 레코드를 업데이트 하기 위한 인터페이스입니다.  
  
 DDX 함수를 사용할 수 있습니다 **COleDbRecordView** 를 데이터베이스 레코드 집합에서 직접 데이터를 가져와 대화 상자 컨트롤에 표시 합니다. 사용 해야는 **DDX_\* ** 메서드 (예: `DDX_Text`)이 아니라는 **DDX_Field\* ** 함수 (같은 `DDX_FieldText`)와 **COleDbRecordView**. `DDX_FieldText`작동 하지 것입니다 **COleDbRecordView** 때문에 `DDX_FieldText` 형식의 추가 인수 **CRecordset\* ** (에 대 한 `CRecordView`) 또는 **CDaoRecordset\* ** (에 대 한 `CDaoRecordView`).  
  
> [!NOTE]
>  클래스를 사용 하 여 OLE DB 소비자 템플릿 클래스를 사용 하지 않고 데이터 액세스 개체 (DAO) 클래스와 작업 하는 경우 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 대신 합니다. 자세한 내용은 문서를 참조 하십시오. [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 `COleDBRecordView`레코드 뷰 사용자 인터페이스를 업데이트할 수 있도록 행 집합에서 사용자의 위치는 추적 합니다. 레코드 뷰 사용자 인터페이스 개체 â € 사용 하지 않도록 설정 하면 행 집합의 한쪽 끝을 이동할 때 "메뉴 항목 또는 도구 모음 단추를 â € 같은" 이동 하기 위한 같은 방향에 대 한 자세한 합니다.  
  
 행 집합 클래스에 대 한 자세한 내용은 참조는 [를 사용 하 여 OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md) 문서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 `COleDBRecordView` 개체를 생성합니다.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTemplateName`  
 대화 상자 템플릿 리소스의 이름에 해당 하는 null로 끝나는 문자열을 포함 합니다.  
  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID 번호를 포함합니다.  
  
### <a name="remarks"></a>주의  
 파생 된 형식의 개체를 만들 때 `COleDBRecordView`, view 개체를 만들고 보기의 기반이 되는 대화 상자 리소스를 식별 하는 생성자 중 하나를 호출 합니다. (생성자에는 문자열을 인수로 전달) 이름 또는 ID (pass 인수로 부호 없는 정수)가 리소스를 식별할 수 있습니다.  
  
> [!NOTE]
>  파생된 클래스의 *해야* 자체 생성자를 제공 합니다. 생성자에는 생성자를 호출 `COleDBRecordView::COleDBRecordView`, 리소스 이름 또는 ID를 인수로 사용 합니다.  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 에 대 한 핸들을 반환 된 **CRowset<> </> ** 레코드 보기와 연결 된 개체입니다.  
  
```  
virtual CRowset<>* OnGetRowset(Â) = 0;  
 
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 생성 또는 행 집합 개체를 가져오고,에 대 한 핸들을 반환 하려면이 멤버 함수를 재정의 해야 합니다. 클래스 마법사와 레코드 뷰 클래스를 선언 하는 경우 마법사는 기본 재정의를 작성 합니다. 클래스 마법사의 기본 구현은 있을 경우 레코드 뷰에 저장 된 행 집합 핸들을 반환 합니다. ClassWizard 및 호출을 사용 하 여 지정한 형식의 행 집합 개체를 생성 그렇지 않은 경우 해당 **열고** 멤버 함수는 테이블을 열거나 쿼리를 실행 하 고 다음 개체에 대 한 핸들을 반환 합니다.  
  
> [!NOTE]
>  MFC 7.0 이전의 `OnGetRowset` 에 대 한 포인터를 반환 합니다. `CRowset`합니다. 호출 하는 코드가 있으면 `OnGetRowset`, 서식 파일 형식의 클래스에 반환 형식을 변경 해야 할 **CRowset<>**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&38;](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 자세한 내용 및 예제에 대 한 문서를 참조 [레코드 뷰: 레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md)합니다.  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 해당 필드는 레코드의 컨트롤에 보기를 표시 및 행 집합에서 다른 레코드로 이동 합니다.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDMoveCommand`  
 다음 표준 명령 ID 값 중 하나입니다.  
  
- `ID_RECORD_FIRST`Â 레코드 집합의 첫 번째 레코드를 Â Â 이동 합니다.  
  
- `ID_RECORD_LAST`Â Â Â 이동 레코드 집합의 마지막 레코드입니다.  
  
- `ID_RECORD_NEXT`Â 레코드 집합의 다음 레코드로 Â Â 이동 합니다.  
  
- `ID_RECORD_PREV`Â 레코드 집합의 이전 레코드로 Â Â 이동 합니다.  
  
### <a name="return-value"></a>반환 값  
 이동에 성공 하면 0이 아닌 그렇지 않으면 0이 고 이동 요청은 거부 되었습니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 적절 한 호출 **이동** 의 멤버 함수는 `CRowset` 레코드 보기와 연결 된 개체입니다.  
  
 기본적으로 `OnMove` 사용자 레코드 보기에서 변경 된 경우 데이터 소스에서 현재 레코드를 업데이트 합니다.  
  
 응용 프로그램 마법사는 첫 번째 레코드, 마지막 레코드, 다음 레코드 및 이전 레코드 메뉴 항목과 함께 메뉴 리소스를 만듭니다. 도킹 가능한 도구 모음 옵션을 선택 하면 응용 프로그램 마법사는이 명령에 해당 하는 단추가 포함 된 도구 모음도 만듭니다.  
  
 레코드 집합의 마지막 레코드를 지난 이동 하는 경우 레코드 뷰 계속 마지막 레코드를 표시 합니다. 첫 번째 레코드를 지 나 뒤로 이동 하는 경우 첫 번째 레코드를 표시 하는 레코드 뷰 계속 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




