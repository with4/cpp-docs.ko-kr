---
title: "messages_byname 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f8aebacee06decfefcbfa81b93f7773e99e7f5e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="messagesbyname-class"></a>messages_byname 클래스
파생된 템플릿 클래스는 지정된 로캘의 메시지 패싯으로 사용하여 지역화된 메시지를 검색할 수 있는 개체에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Locname`  
 명명된 로캘입니다.  
  
 `_Refs`  
 초기 참조 개수입니다.  
  
## <a name="remarks"></a>설명  
 해당 동작은 명명된 로캘 `_Locname`에 따라 결정됩니다. 각 생성자는 [messages](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`)를 통해 기본 개체를 초기화합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



