---
title: 'Cutlprops:: Oninterfacerequested | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- OnInterfaceRequested method
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50a1f17294a91446e71a51ffdac6c5aec83f2c9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099773"
---
# <a name="cutlpropsoninterfacerequested"></a>CUtlProps::OnInterfaceRequested
소비자 메서드를 호출할 때 개체 중 하나에서 생성 인터페이스는 선택적 인터페이스에 대 한 요청을 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 요청된 된 인터페이스에 대 한 IID입니다. 자세한 내용은 설명을 참조는 `riid` 의 매개 변수 `ICommand::Execute` 에 *OLE DB Programmer's Reference* (에 *MDAC SDK*).  
  
## <a name="remarks"></a>설명  
 **OnInterfaceRequested** 소비자 메서드를 호출할 때 개체 중 하나에서 생성 인터페이스는 선택적 인터페이스에 대 한 소비자 요청을 처리 (예: **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset`, 또는 `ICommand`). 요청된 된 인터페이스에 대 한 해당 OLE DB 속성을 설정 합니다. 예를 들어 소비자 요청 **IID_IRowsetLocate**, **OnInterfaceRequested** 설정는 **DBPROP_IRowsetLocate** 인터페이스입니다. 이렇게 행 집합을 만드는 동안 올바른 상태를 유지 관리 합니다.  
  
 이 메서드는 소비자를 호출할 때 **iopenrowset:: Openrowset** 또는 `ICommand::Execute`합니다.  
  
 소비자 개체를 엽니다 하는 선택적 인터페이스를 요청 하는 경우 공급자 해당 인터페이스를와 연결 된 속성을 설정 해야 `VARIANT_TRUE`합니다. 속성 관련 처리를 허용할지 **OnInterfaceRequested** 공급자의 이전에 호출 됩니다 **Execute** 메서드를 호출 합니다. 기본적으로 **OnInterfaceRequested** 다음 인터페이스를 처리 합니다.  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 다른 인터페이스를 처리 하려는 경우 프로세스 함수에 데이터 원본, 세션, 명령 또는 행 집합 클래스에이 함수를 재정의 합니다. 재정의 속성을 설정를 설정 하는 모든 연결 된 속성을 확인 하는 일반 set/get 속성 인터페이스를 통과 해야 (참조 [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CUtlProps 클래스](../../data/oledb/cutlprops-class.md)