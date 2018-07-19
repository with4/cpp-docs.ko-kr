---
title: _com_error::_com_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec16faa9881fc1c69dca5f8f39b8797cf0fcff0d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944473"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft 전용**  
  
 `_com_error` 개체를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
_com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false) throw( );  

_com_error( const _com_error& that ) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hr*  
 HRESULT 정보입니다.  
  
 *perrinfo*  
 `IErrorInfo` 개체  
  
 `bool fAddRef=false`  
 Null이 아닌에서 AddRef를 호출 하도록 생성자가 `IErrorInfo` 인터페이스입니다. 이를 통해 인터페이스의 소유권이 `_com_error` 개체로 전달되는 일반적인 경우에 참조 횟수를 정확하게 셀 수 있습니다.  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 경우 원하지 않는 소유권을 전송 하는 코드를 `_com_error` 개체 및 `AddRef` 오프셋 하는 데 필요한를 `Release` 에 `_com_error` 소멸자 개체를 다음과 같이 작성:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *는*  
 기존 `_com_error` 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 지정 된 HRESULT를 및 선택적 새 개체를 만들고 `IErrorInfo` 개체입니다. 두 번째 생성자는 기존 `_com_error` 개체의 복사본을 만듭니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)