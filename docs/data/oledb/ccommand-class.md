---
title: CCommand 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
dev_langs:
- C++
helpviewer_keywords:
- CCommand class
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 667e86c173a7001ae22036cb1f0dd8f3fbfcf6a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096901"
---
# <a name="ccommand-class"></a>CCommand 클래스
설정 하 고 명령을 실행 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CNoAccessor,  
          template <typename T> class TRowset = CRowset,  
          class TMultiple = CNoMultipleResults>  
class CCommand :   
           public CAccessorRowset <TAccessor, TRowset>,  
           public CCommandBase,  
           public TMultiple  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스의 형식 (같은 `CDynamicParameterAccessor`, `CDynamicStringAccessor`, 또는 `CEnumeratorAccessor`) 명령에서 사용 되도록 합니다. 기본값은 `CNoAccessor`는 클래스 하지 매개 변수를 지원 하거나 지정 열을 출력 합니다.  
  
 `TRowset`  
 행 집합 클래스의 유형 (예: `CArrayRowset` 또는 `CNoRowset`) 명령에서 사용 되도록 합니다. 기본값은 `CRowset`입니다.  
  
 `TMultiple`  
 여러 개의 결과 반환할 수 있는 OLE DB 명령을 사용 하려면 지정 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)합니다. 그렇지 않은 경우 사용 하 여 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)합니다. 자세한 내용은 참조 [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[닫기](../../data/oledb/ccommand-close.md)|현재 명령을 닫습니다.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|여러 결과 사용 하 여 설정 하는 경우에 다음 결과 인출 합니다.|  
|[열기](../../data/oledb/ccommand-open.md)|실행 하 고 필요에 따라 명령을 바인딩합니다.|  
  
### <a name="inherited-methods"></a>상속 된 메서드  
  
|||  
|-|-|  
|[만들기](../../data/oledb/ccommand-create.md)|지정된 된 세션에 대 한 새로운 명령 만들기 다음 명령 텍스트를 설정 합니다.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|새 명령을 만듭니다.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|명령의 매개 변수, 속성 이름 및 해당 종류의 목록을 가져옵니다.|  
|[준비](../../data/oledb/ccommand-prepare.md)|유효성을 검사 하 고 현재 명령을 최적화 합니다.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|필요한 경우 매개 변수 접근자를 해제 한 다음 명령을 해제 합니다.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|각 명령 매개 변수의 네이티브 유형을 지정합니다.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|현재 명령 실행 계획을 삭제 합니다.|  
  
## <a name="remarks"></a>설명  
 매개 변수 기반 작업을 수행 하거나 명령을 실행 해야 할 때이 클래스를 사용 합니다. 단순 행 집합을 단순히 필요 [CTable](../../data/oledb/ctable-class.md) 대신 합니다.  
  
 접근자 클래스 사용 하는 매개 변수 및 데이터를 바인딩하는 방법을 결정 합니다.  
  
 사용 하는 수 없는 저장된 프로시저 OLE DB provider for Jet 해당 공급자가 지원 하지 않으므로 저장 프로시저 (쿼리 문자열에 상수만 사용할 수)입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)