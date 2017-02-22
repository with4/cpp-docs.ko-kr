---
title: "ComPtr::As 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As 메서드"
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtr::As 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 템플릿 매개 변수로 식별된 인터페이스를 나타내는 ComPtr 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `U`  
 매개 변수도 표현 하는 인터페이스 `p`합니다.  
  
 `p`  
 매개 변수로 지정 된 인터페이스를 나타내는 ComPtr 개체 `U`합니다. 매개 변수 `p` 현재 ComPtr 개체를 참조 하지 않아야 합니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 서식 파일은 기능을 지 원하는 c + + 언어와 같은 한 내부 도우미 특수화는 [자동](../cpp/auto-cpp.md) 형식 추론 키워드입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)