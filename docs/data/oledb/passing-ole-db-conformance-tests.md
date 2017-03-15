---
title: "OLE DB 적합성 테스트 통과 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "적합성 테스트"
  - "규칙 테스트[OLE DB]"
  - "OLE DB 공급자, 테스트"
  - "공급자 테스트"
  - "테스트, OLE DB 공급자"
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB 적합성 테스트 통과
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공급자를 보다 일관되게 만들기 위해 Data Access SDK는 OLE DB 규칙 테스트 집합을 제공합니다.  이 테스트는 공급자의 모든 측면을 테스트하므로 공급자가 예상대로 작동하는지 적절히 확인할 수 있습니다.  Microsoft Data Access SDK에서 OLE DB 규칙 테스트를 찾을 수 있습니다.  이 단원에서는 규칙 테스트를 통과하기 위해 수행해야 할 작업에 중점을 두고 설명합니다.  OLE DB 규칙 테스트 실행에 대한 자세한 내용은 SDK를 참조하십시오.  
  
## 규칙 테스트 실행  
 Visual C\+\+ 6.0에서는 OLE DB 공급자 템플릿에 다양한 후크 함수가 추가되어 값과 속성을 확인할 수 있습니다.  이러한 대부분의 함수는 규칙 테스트를 위해 추가된 것입니다.  
  
> [!NOTE]
>  OLE DB 규칙 테스트를 통과하려면 몇 가지 유효성 검사 함수를 추가해야 합니다.  
  
 이 공급자는 두 가지 유효성 검사 루틴을 필요로 합니다.  첫 번째 루틴은 `CRowsetImpl::ValidateCommandID`이며, 행 집합 클래스의 일부입니다.  이 루틴은 공급자 템플릿이 행 집합을 만드는 동안 호출됩니다.  샘플에서는 이 루틴을 사용하여 소비자에게 인덱스를 지원하지 않는다는 것을 알립니다.  첫 번째 호출은 `CRowsetImpl::ValidateCommandID`로 호출됩니다. 공급자는 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)의 `CMyProviderRowset`에 대한 인터페이스 맵에 추가된 **\_RowsetBaseClass** 형식 정의를 사용하므로 긴 템플릿 인수 줄을 직접 입력할 필요가 없습니다.  그런 다음 인덱스 매개 변수가 **NULL**이 아니면 **DB\_E\_NOINDEX**를 반환합니다. 이는 소비자가 인덱스를 사용하려 한다는 것을 나타냅니다.  명령 ID에 대한 자세한 내용은 OLE DB 사양에서 **IOpenRowset::OpenRowset**을 참조하십시오.  
  
 다음 코드는 **ValidateCommandID** 유효성 검사 루틴입니다.  
  
```  
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
  
 공급자 템플릿은 누군가가 **DBPROPSET\_ROWSET** 그룹의 속성을 변경할 때마다 `OnPropertyChanged` 메서드를 호출합니다.  다른 그룹의 속성을 처리하려면 적절한 개체에 그룹을 추가합니다. 즉, **DBPROPSET\_SESSION**을 검사하면 `CMyProviderSession` 클래스를 검사하게 됩니다.  
  
 코드는 먼저 속성이 다른 속성에 연결되었는지 확인합니다.  속성이 다른 속성에 연결되어 있으면 **DBPROP\_BOOKMARKS** 속성을 True로 설정합니다.  OLE DB 사양의 부록 C에서 속성에 대한 자세한 내용을 참조할 수 있습니다.  이 정보를 보고 속성이 다른 속성에 연결되었는지 알 수도 있습니다.  
  
 코드에 `IsValidValue` 루틴을 추가할 수도 있습니다.  템플릿은 속성을 설정하려고 할 때 `IsValidValue`를 호출합니다.  속성 값을 설정할 때 추가 처리가 필요할 경우에는 이 메서드를 재정의합니다.  각 속성 집합에 이러한 메서드 중 하나를 사용할 수 있습니다.  
  
## 스레딩 문제  
 기본적으로 ATL OLE DB 공급자 마법사의 ATL OLE DB 공급자 마법사는 공급자가 아파트 모델에서 실행될 수 있도록 코드를 생성합니다.  이 코드를 규칙 테스트와 함께 실행하려고 하면 처음에는 실패합니다.  이는 OLE DB 규칙 테스트를 실행하는 데 사용되는 Ltm.exe 도구가 기본적으로 자유 스레드로 설정되어 있기 때문입니다.  ATL OLE DB 공급자 마법사의 코드는 성능 및 사용상의 편의를 위해 기본적으로 아파트 모델로 설정되어 있습니다.  
  
 이 문제를 해결하려면 LTM을 변경하거나 공급자를 변경합니다.  
  
#### LTM을 변경하여 아파트 스레드 모드에서 실행하려면  
  
1.  LTM의 기본 메뉴에서 **Tools**를 클릭한 다음 **Options**를 클릭합니다.  
  
2.  **General** 탭에서 스레딩 모델을 **Free Threaded**에서 **Apartment Threaded**로 변경합니다.  
  
 공급자를 변경하여 자유 스레드 모드에서 실행하려면  
  
-   공급자 프로젝트에서 `CComSingleThreadModel`의 모든 인스턴스를 검색한 다음 데이터 소스, 세션 개체 및 행 집합 헤더에 있는 `CComMultiThreadModel`과 바꿉니다.  
  
-   .rgs 파일에서 스레딩 모델을 **Apartment**에서 **Both**로 변경합니다.  
  
-   자유 스레드 프로그래밍에서는 정확한 프로그래밍 규칙\(작성 시 잠금\)을 따릅니다.  
  
## 참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)