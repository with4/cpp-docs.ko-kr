---
title: 'Cutlprops:: Onpropertychanged | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c9b52949db714206b6118000d004c6248b7d6235
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100501"
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
연결 된 속성을 처리 하는 속성을 설정한 후 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iCurSet`  
 속성 집합 배열;에 대 한 인덱스 하나의 속성 집합이 있는 경우 0입니다.  
  
 `pDBProp`  
 속성 ID와에 새 값을 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다. 기본 반환 값은 `S_OK`합니다.  
  
## <a name="remarks"></a>설명  
 책갈피나 다른 속성의 값에 의존 하는 값을 포함 하는 업데이트와 같은 연결 된 속성을 처리 하려는 경우이 함수를 재정의 해야 합니다.  
  
## <a name="example"></a>예제  
 이 함수를 사용자에서 속성 ID를 가져옵니다는 `DBPROP*` 매개 변수입니다. 이제 체인으로 연결 속성에 대해 ID와 비교 하는 것이 같습니다. 속성을 찾을 때 `SetProperties` 속성을 다른 속성과 함께에서 설정 될 것으로 호출 합니다. 이 경우 하나를 가져오면는 `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, 또는 `DBPROP_ORDEREDBOOKMARKS` 속성을 하나 설정할 수 있습니다는 `DBPROP_BOOKMARKS` 속성입니다.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)