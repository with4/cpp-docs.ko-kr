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
ms.openlocfilehash: 0288e1517bf89ec6ff8a2067311c3641d8d7113c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340918"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 적합성 테스트 통과
Data Access SDK에는 공급자를 일관 되 게 하려면 OLE DB 적합성 테스트 집합을 제공 합니다. 테스트는 공급자의 모든 측면을 확인 하 고 공급자 함수를 예상 하는 적절 한 보증을 제공 합니다. Microsoft Data Access SDK에 OLE DB 적합성 테스트를 찾을 수 있습니다. 이 섹션에서는 적합성 테스트 통과 위해 수행 해야 할 작업에 중점을 둡니다. OLE DB 적합성 테스트를 실행 하는 방법에 대 한 내용은 SDK를 참조 하세요.  
  
## <a name="running-the-conformance-tests"></a>규칙 테스트 실행  
 Visual c + + 6.0 OLE DB 공급자 템플릿 다양 한 값과 속성을 확인할 수 있도록 후크 함수를 추가 합니다. 이러한 함수 중 대부분은 규칙 테스트에 대 한 응답에 추가 되었습니다.  
  
> [!NOTE]
>  OLE DB 적합성 테스트 통과를 공급자에 대해 여러 유효성 검사 함수를 추가 해야 합니다.  
  
 이 공급자에는 두 가지 유효성 검사 루틴에 필요합니다. 첫 번째 루틴 `CRowsetImpl::ValidateCommandID`, 행 집합 클래스의 일부입니다. 행 집합을 만드는 동안 공급자 템플릿에 의해 호출 됩니다. 샘플이이 루틴을 사용 하 여 인덱스를 지원 하지 않습니다 소비자에 게 알립니다. 첫 번째 호출 하는 것 `CRowsetImpl::ValidateCommandID` (공급자를 사용 하는 참고 합니다 `_RowsetBaseClass` 의 인터페이스 맵에 추가 하는 typedef `CMyProviderRowset` 에서 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)이므로 템플릿의 해당 긴 줄을 입력할 필요가 없습니다 인수)입니다. 인덱스 매개 변수가 NULL이 아닌 경우 DB_E_NOINDEX를이 어 반환 (나타냅니다는 소비자가 알아서 인덱스 사용). 명령 Id에 대 한 자세한 내용은 OLE DB 사양을 참조 하 고 검색할 `IOpenRowset::OpenRowset`합니다.  
  
 다음 코드는는 `ValidateCommandID` 유효성 검사 과정:  
  
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
  
 공급자 템플릿 호출의 `OnPropertyChanged` 에서 속성을 변경 될 때마다 메서드는 `DBPROPSET_ROWSET` 그룹입니다. 적절 한 개체에 추가할 다른 그룹에 대 한 속성을 처리 하려는 경우 (즉, `DBPROPSET_SESSION` 검사를 진행 합니다 `CMyProviderSession` 클래스).  
  
 먼저 코드 속성에 다른 연결 되었는지 여부를 확인 합니다. 속성에 연결 될 경우에 설정 된 `DBPROP_BOOKMARKS` 속성을 true로 합니다. OLE DB 사양의 부록 C는 속성에 대 한 정보를 포함합니다. 이 정보 또한 알려 속성에 다른 연결 되었는지 여부입니다.  
  
 추가할 수도 있습니다는 `IsValidValue` 일상적인 코드입니다. 템플릿 호출 `IsValidValue` 속성을 설정 하려고 할 때입니다. 속성 값을 설정 하는 경우 추가 처리가 필요한 경우이 메서드를 재정의 됩니다. 각 속성 집합에 대해 이러한 메서드 중 하나가 있습니다.  
  
## <a name="threading-issues"></a>스레딩 문제  
 기본적으로 OLE DB 공급자 마법사 ATL OLE DB 공급자 마법사의 아파트 모델에서 실행 하는 공급자에 대 한 코드를 생성 합니다. 규칙 테스트를 사용 하 여이 코드를 실행 하려고 하면 처음에 오류를 가져옵니다. 이 Ltm.exe, OLE DB 적합성 테스트를 실행 하는 데이 도구를 무료 기본값으로 하기 때문에 스레드입니다. OLE DB 공급자 마법사 코드 아파트 모델 성능 및 사용 편의성에 대 한 기본값으로 사용 됩니다.  
  
 이 문제를 해결 하려면 LTM 변경 또는 공급자를 변경할 수 있습니다.  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>모드를 스레드 아파트에서 실행 되도록 LTM를 변경 하려면  
  
1.  LTM 주 메뉴에서 클릭 **도구**를 클릭 하 고 **옵션**합니다.  
  
2.  에 **일반** 탭에서 스레딩 모델을 변경 **자유 스레드** 하 **Apartment Threaded**합니다.  
  
 변경 하려면 사용 가능한 스레드 모드에서 실행 되도록 공급자:  
  
-   공급자 프로젝트의 모든 인스턴스에 대 한 검색 `CComSingleThreadModel` 바꿉니다 `CComMultiThreadModel`에 데이터 원본, 세션 및 행 머리글에 합니다.  
  
-   .Rgs 파일에에서 스레딩 모델을 변경 **아파트** 하 **둘 다**합니다.  
  
-   자유 스레드 프로그래밍 (즉, 쓰기 잠금)에 따라 올바른 프로그래밍 규칙.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)