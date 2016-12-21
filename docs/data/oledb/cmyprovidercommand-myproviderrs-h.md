---
title: "CMyProviderCommand(MyProviderRS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyprovidercommand"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MyProviderRS.H의 CMyProviderCommand 클래스"
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderCommand(MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMyProviderCommand` 클래스는 공급자 명령 개체에 대한 구현입니다.  이 클래스는 `IAccessor`, `ICommandText` 및 **ICommandProperties** 인터페이스에 대한 구현을 제공합니다.  `IAccessor` 인터페이스는 행 집합의 `IAccessor` 인터페이스와 같습니다.  명령 개체는 접근자를 사용하여 매개 변수에 대한 바인딩을 지정하고,  행 집합 개체는 접근자를 사용하여 출력 열에 대한 바인딩을 지정합니다.  `ICommandText` 인터페이스는 명령을 텍스트로 지정할 때 유용합니다.  다음 예제에서는 나중에 사용자 지정 코드를 추가할 때 `ICommandText` 인터페이스를 사용합니다. 이 예제에서는 `ICommand::Execute` 메서드도 재정의합니다.  **ICommandProperties** 인터페이스는 명령 개체와 행 집합 개체에 대한 모든 속성을 처리합니다.  
  
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
  
 `IAccessor` 인터페이스는 명령과 행 집합에 사용된 모든 바인딩을 관리합니다.  소비자는 **DBBINDING** 구조의 배열을 사용하여 **IAccessor::CreateAccessor**를 호출합니다.  각 **DBBINDING** 구조에는 열 바인딩 처리 방법에 대한 정보\(형식, 길이 등\)가 있습니다.  공급자는 이 구조를 받은 다음 데이터 전송 방법과 변환이 필요한 지 여부를 결정합니다.  `IAccessor` 인터페이스는 명령의 모든 매개 변수를 처리하기 위해 명령 개체에서 사용됩니다.  
  
 또한 명령 개체는 `IColumnsInfo` 구현을 제공합니다.  OLE DB에는 `IColumnsInfo` 인터페이스가 필요합니다.  이 인터페이스는 소비자가 명령에서 매개 변수에 대한 정보를 검색할 수 있도록 합니다.  행 집합 개체는 `IColumnsInfo` 인터페이스를 사용하여 출력 열에 대한 정보를 공급자에게 반환합니다.  
  
 또한 공급자에는 `IObjectWithSite`라는 인터페이스가 있습니다.  `IObjectWithSite` 인터페이스는 ATL 2.0에서 구현되었으며 구현자가 자체 정보를 자식 인터페이스에 전달할 수 있도록 합니다.  명령 개체는 `IObjectWithSite` 정보를 사용하여 생성된 행 집합 개체를 누가 만들었는지 식별합니다.  
  
## 참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)