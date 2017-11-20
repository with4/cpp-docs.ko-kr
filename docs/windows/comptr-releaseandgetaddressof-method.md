---
title: "Comptr:: Releaseandgetaddressof 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6711cc93071c1e260a5d216a6ad21add9c00540
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf 메서드
이 ComPtr과 연결된 인터페이스를 해제한 다음 해제된 인터페이스에 대한 포인터를 포함하는, [ptr_](../windows/comptr-ptr-data-member.md) 데이터 멤버의 주소를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>반환 값  
 주소는 [ptr_](../windows/comptr-ptr-data-member.md) 이 ComPtr의 데이터 멤버입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::ptr_ 데이터 멤버](../windows/comptr-ptr-data-member.md)