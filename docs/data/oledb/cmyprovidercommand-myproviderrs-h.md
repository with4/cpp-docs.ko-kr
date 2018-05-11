---
title: CMyProviderCommand (MyProviderRS.H) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidercommand
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8c18742d9b3b1039033ad8d42939e0f5a4578fbb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmyprovidercommand-myproviderrsh"></a>CMyProviderCommand(MyProviderRS.H)
`CMyProviderCommand` 클래스는 공급자 명령 개체에 대 한 구현 합니다. 에 대 한 구현을 제공는 `IAccessor`, `ICommandText`, 및 **ICommandProperties** 인터페이스입니다. `IAccessor` 인터페이스 행 집합에 있는 것과 같습니다. 명령 개체가 매개 변수에 대 한 바인딩을 지정 하는 접근자를 사용 합니다. 행 집합 개체 하는 데 사용 출력 열에 대 한 바인딩을 지정 합니다. `ICommandText` 인터페이스는 명령을 텍스트로 지정할 때 유용 합니다. 사용 하 여이 예제는 `ICommandText` 사용자 지정 코드를 추가 하는 경우 나중에 인터페이스; 또한 재정의 `ICommand::Execute` 메서드. **ICommandProperties** 인터페이스의 모든 명령 및 행 집합 개체에 대 한 속성을 처리 합니다.  
  
```  
// CMyProviderCommand  
class ATL_NO_VTABLE CMyProviderCommand :   
class ATL_NO_VTABLE CMyProviderCommand :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IAccessorImpl<CMyProviderCommand>,  
   public ICommandTextImpl<CMyProviderCommand>,  
   public ICommandPropertiesImpl<CMyProviderCommand>,  
   public IObjectWithSiteImpl<CMyProviderCommand>,  
   public IConvertTypeImpl<CMyProviderCommand>,  
   public IColumnsInfoImpl<CMyProviderCommand>  
```  
  
 `IAccessor` 인터페이스 명령 및 행 집합에 사용 된 모든 바인딩을 관리 합니다. 소비자 호출 **iaccessor:: Createaccessor** 의 배열을 사용 하 여 **DBBINDING** 구조입니다. 각 **DBBINDING** 구조 (예: 형식 및 길이)의 열 바인딩 처리 방법에 대 한 정보를 포함 합니다. 공급자 구조를 받은 다음 데이터를 전송 하는 방법 및 변환이 필요한 지 여부를 결정 합니다. `IAccessor` 인터페이스 명령에 모든 매개 변수를 처리 명령 개체에서 사용 됩니다.  
  
 또한 명령 개체의 구현을 제공 `IColumnsInfo`합니다. OLE DB 필요는 `IColumnsInfo` 인터페이스입니다. 이 인터페이스는 명령에서 매개 변수에 대 한 정보를 검색 하는 소비자를 허용 합니다. 행 집합 개체가 사용 하 여 `IColumnsInfo` 출력 열에 대 한 정보는 공급자를 반환 하는 인터페이스입니다.  
  
 공급자 라는 인터페이스가 포함 `IObjectWithSite`합니다. `IObjectWithSite` 인터페이스 ATL 2.0에서 구현 된 알리고 구현 자가 해당 자식에 자체에 대 한 정보를 전달 합니다. 사용 하 여 명령 개체는 `IObjectWithSite` 하나를 정보는 사용자가 만든 사람에 대 한 행 집합 개체를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)