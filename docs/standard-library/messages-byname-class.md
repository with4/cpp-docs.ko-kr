---
title: "messages_byname 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: a94395023ff39e787f2fdc23dfe3fe4ccb57ff4c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

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




