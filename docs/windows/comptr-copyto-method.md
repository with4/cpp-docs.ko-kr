---
title: "ComPtr::CopyTo 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo 메서드"
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::CopyTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 포인터에 대한 ComPtr과 관련된 지정된 인터페이스 또는 현재 인터페이스를 복하합니다.  
  
## 구문  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### 매개 변수  
 `U`  
 형식 이름입니다.  
  
 `ptr`  
 이 작업이 완료될 때 요청된 인터페이스에 대한 포인터입니다.  
  
 `riid`  
 인터페이스 ID  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 암시적 QueryInterface 작업 실패를 나타내는 HRESULT입니다.  
  
## 설명  
 첫 번째 함수가 이 ComPtr와 관련된 인터페이스 포인터의 복사본을 반환합니다.  이 함수는 항상 S\_OK를 반환합니다.  
  
 이 ComPtr로 지정된 인터페이스와 연결 된 인터페이스에서 QueryInterface 작업을 수행 하는 두 번째 함수는 `riid` 매개 변수입니다.  
  
 이 ComPtr의 내부 인터페이스와 연결 된 인터페이스에서 QueryInterface 작업을 수행 하는 세 번째 함수는 `U` 매개 변수입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)