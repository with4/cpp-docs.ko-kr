---
title: "ComPtr::operator&amp; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator& 연산자"
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator&amp; 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`ComPtr` 개체와 연관된 인터페이스를 해제하고 그때 `ComPtr` 개체의 주소를 검색합니다.  
  
## 구문  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## 반환 값  
 현재 `ComPtr` 에서 약화된 참조입니다.  
  
## 설명  
 인터페이스 포인터에 대한 참조를 해제한 점에서, [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) 는 이 메서드와 다릅니다.  인터페이스 포인터의 주소를 필요로 하지만 이 인터페이스를 헤제하길 원하지 않을 경우, `ComPtr::GetAddressOf` 사용합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)