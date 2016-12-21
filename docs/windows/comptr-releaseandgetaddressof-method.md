---
title: "ComPtr::ReleaseAndGetAddressOf 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf 메서드"
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ReleaseAndGetAddressOf 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 ComPtr에 연결 된 인터페이스를 해제하고 주소를 검색한 다음, [ptr\_](../windows/comptr-ptr-data-member.md) 출시 된 인터페이스에 대한 포인터를 포함하는 데이터 멤버입니다.  
  
## 구문  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## 반환 값  
 [ptr\_](../windows/comptr-ptr-data-member.md) 데이터의 주소는 ComPtr이 데이터 멤버입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::ptr\_ 데이터 멤버](../windows/comptr-ptr-data-member.md)