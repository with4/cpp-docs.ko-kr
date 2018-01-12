---
title: "marshal_context 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b59dfa82563a0c115f521bb881411981a30efc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontext-class"></a>marshal_context 클래스
이 클래스는 네이티브 및 관리 환경 간에 데이터를 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>설명  
 사용 하 여 `marshal_context` 컨텍스트 해야 하는 데이터 변환에 대 한 클래스입니다. 참조 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md) 는 변환에는 컨텍스트가 필요 하 고 어떤 마샬링 파일에 포함 되도록 하는 방법에 대 한 자세한 내용은 합니다. 마샬링 한 컨텍스트를 사용 하는 경우의 결과 유효 기간만 `marshal_context` 개체를 제거 합니다. 사용자의 결과 유지 하려면 데이터를 복사 해야 합니다.  
  
 동일한 `marshal_context` 에 여러 개의 데이터 변환을 사용할 수 있습니다. 이런이 방식으로 컨텍스트를 다시 사용 이전 마샬링 호출의 결과 영향을 주지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, 또는 \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>참고 항목  
 [C + + 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)