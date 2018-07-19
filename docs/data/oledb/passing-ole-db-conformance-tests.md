---
title: OLE DB 적합성 테스트 통과 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11677e6295956de768c7ebc0c113d775b066bb0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110466"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 적합성 테스트 통과
Data Access SDK 공급자를 보다 일관 되 게 하려면 OLE DB 적합성 테스트 집합이 제공 합니다. 테스트는 공급자의 모든 측면을 확인 하 고 예상 대로 프로그램 공급자 작동 하는지 적절히 제공 합니다. Microsoft Data Access SDK에 OLE DB 적합성 테스트를 찾을 수 있습니다. 이 섹션 규칙 테스트를 통과 하기 위해 수행 해야 하는 것에 중점을 둡니다. OLE DB 적합성 테스트를 실행 하는 방법에 대 한 정보, SDK를 참조 하십시오.  
  
## <a name="running-the-conformance-tests"></a>규칙 테스트 실행  
 Visual c + + 6.0 OLE DB 공급자 템플릿 값과 속성을 확인할 수 있도록 후크 함수가 여러를 추가 합니다. 이러한 기능의 대부분 규칙 테스트에 대 한 응답에 추가 되었습니다.  
  
> [!NOTE]
>  OLE DB 적합성 테스트 통과 하 여 공급자에 대 한 여러 가지 유효성 검사 기능을 추가 해야 합니다.  
  
 이 공급자는 두 가지 유효성 검사 루틴을 필요로합니다. 첫 번째 루틴 `CRowsetImpl::ValidateCommandID`, 행 집합 클래스의 일부입니다. 행 집합을 만드는 동안 공급자 템플릿에 의해 호출 됩니다. 이 샘플에 인덱스를 지원 하지 않는 소비자에 게 알릴이 루틴을 사용 합니다. 첫 번째 호출 하는 것 `CRowsetImpl::ValidateCommandID` (공급자를 사용 하는 **호출** typedef에 대 한 인터페이스 맵에 추가 `CMyProviderRowset` 에 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)를 않아도 되므로 템플릿 인수 번째 입력). 그런 다음 반환 **DB_E_NOINDEX** 인덱스 매개 변수가 없으면 **NULL** (나타냅니다 소비자에서 우리는 인덱스를 사용 하려는). 명령 Id에 대 한 자세한 내용은 OLE DB 사양을 참조를 찾아서 **iopenrowset:: Openrowset**합니다.  
  
 다음 코드는는 **ValidateCommandID** 유효성 검사 루틴:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 공급자 템플릿 호출의 `OnPropertyChanged` 에서 속성을 변경 될 때마다 메서드는 **DBPROPSET_ROWSET** 그룹입니다. 적절 한 개체에 추가할 다른 그룹에 대 한 정보를 저장 하려는 경우 (즉, **DBPROPSET_SESSION** 에 `CMyProviderSession` 클래스).  
  
 코드는 먼저 속성에 다른 연결 되었는지 여부를 확인 합니다. 속성을 연결 하는 경우에 설정 된 **DBPROP_BOOKMARKS** 속성을 True로 합니다. OLE DB 사양의 부록 C 속성에 대 한 정보를 포함 합니다. 이 정보 또한 알려 속성에 다른 연결 되었는지 여부.  
  
 추가할 수도 있습니다는 `IsValidValue` 코드에 일상적인 합니다. 템플릿 호출 `IsValidValue` 속성을 설정 하려고 할 때입니다. 속성 값을 설정할 때 추가 처리가 필요한 경우이 메서드를 재정의 합니다. 각 속성 집합에 대 한 이러한 방법 중 하나를 사용할 수 있습니다.  
  
## <a name="threading-issues"></a>스레딩 문제  
 기본적으로는 OLE DB 공급자 마법사 ATL OLE DB 공급자 마법사의 아파트 모델에서 실행 하도록 공급자에 대 한 코드를 생성 합니다. 규칙 테스트와이 코드를 실행 하려고 하면 오류가 처음 발생 합니다. 이 Ltm.exe, OLE DB 적합성 테스트를 실행 하는 데 도구 기본적으로 해제 하기 때문에 스레드입니다. OLE DB 공급자 마법사 코드의 사용 편이성과 성능에 대 한 아파트 모델 기본값으로 사용 됩니다.  
  
 이 문제를 해결 하려면 LTM를 변경 하거나 공급자를 변경할 수 있습니다.  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>모드를 스레드 아파트에서 실행 되도록 LTM를 변경 하려면  
  
1.  LTM 주 메뉴에서 클릭 **도구**, 클릭 하 고 **옵션**합니다.  
  
2.  에 **일반** 탭에서 스레딩 모델을 변경 합니다 **자유 스레드** 를 **Apartment Threaded**합니다.  
  
 변경 하려면 공급자 스레드 무료 모드에서 실행 하려면:  
  
-   공급자 프로젝트에서의 모든 인스턴스에 대 한 검색 `CComSingleThreadModel` 로 바꿉니다 `CComMultiThreadModel`, 데이터 원본, 세션 및 행 집합 헤더에 있습니다.  
  
-   .Rgs 파일에에서 스레딩 모델을 변경 **아파트** 를 **둘 다**합니다.  
  
-   에 따라 올바른 프로그래밍 프로그래밍 규칙 자유 스레드 (즉, 잠금 쓰기 중에).  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)