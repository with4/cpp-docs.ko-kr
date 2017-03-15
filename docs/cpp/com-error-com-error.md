---
title: "_com_error::_com_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error._com_error"
  - "_com_error::_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error 메서드"
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::_com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `_com_error` 개체를 생성합니다.  
  
## 구문  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### 매개 변수  
 `hr`  
 `HRESULT` 정보입니다.  
  
 `perrinfo`  
 **IErrorInfo** 개체입니다.  
  
 **bool fAddRef\=false**  
 생성자가 null이 아닌 **IErrorInfo** 인터페이스에서 AddRef를 호출하도록 합니다.  이를 통해 인터페이스의 소유권이 `_com_error` 개체로 전달되는 일반적인 경우에 참조 횟수를 정확하게 셀 수 있습니다.  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 소유권을 `_com_error` 개체로 이전하는 코드를 원하지 않는 경우 및 `AddRef`가 **릴리스**를 `_com_error` 소멸자에서 오프셋하는 데 필요한 경우, 개체를 다음과 같이 생성합니다.  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 기존 `_com_error` 개체입니다.  
  
## 설명  
 첫 번째 생성자는 `HRESULT` 및 **IErrorInfo** 개체\(선택 사항\)를 사용하여 새 개체를 만듭니다.  두 번째 생성자는 기존 `_com_error` 개체의 복사본을 만듭니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)