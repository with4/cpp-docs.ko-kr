---
title: 'Comptr:: Releaseandgetaddressof 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3bded6992abc5b22e2c02a3364431a3f68b76ad6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649850"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf 메서드
와 연결 된 인터페이스를 해제 **ComPtr** 다음의 주소를 검색 합니다 [ptr_](../windows/comptr-ptr-data-member.md) 출시 된 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>반환 값  
 주소를 [ptr_](../windows/comptr-ptr-data-member.md) 이 데이터 멤버 **ComPtr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::ptr_ 데이터 멤버](../windows/comptr-ptr-data-member.md)