---
title: lock 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a860f79b740e0f34eef33b7a96e0236835f1f6b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129699"
---
# <a name="lock-class"></a>lock 클래스
이 클래스는 여러 스레드에서 개체에 대 한 액세스를 동기화 하기 위한 잠금을 가져오는 자동화 합니다.  생성 될 때는 잠금을 가져올 때 릴리스를 제거 하 고 잠금을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>설명  
 `lock` CLR 개체에 대해서만 사용할 수 있으며 CLR 코드 에서만 사용할 수 있습니다.  
  
 잠금 클래스 사용에 내부적으로 <xref:System.Threading.Monitor> 대 액세스를 동기화 합니다. 동기화에 대 한 자세한 내용은이 항목을 참조 하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [lock](../dotnet/lock.md)   
 [lock 멤버](../dotnet/lock-members.md)