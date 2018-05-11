---
title: ICommandTextImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f49326dba4868ad490dc1a7122eed68271bdfa15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl 클래스
에 대 한 구현을 제공는 [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 명령 클래스에서 파생 된 **ICommandTextImpl**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="interface-methods"></a>인터페이스 메서드  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|텍스트 명령 집합에 대 한 마지막 호출에서 반환 [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)합니다.|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|기존 명령 텍스트를 바꿀 명령 텍스트를 설정 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|명령 텍스트를 저장합니다.|  
  
## <a name="remarks"></a>설명  
 명령에서 필수 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** altdb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)