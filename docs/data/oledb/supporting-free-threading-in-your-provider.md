---
title: "공급자에서 자유 스레딩 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 14bd61bc4f319a50abdbf76d7f6e60e511e57312
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-free-threading-in-your-provider"></a>공급자에서 자유 스레딩 지원
모든 OLE DB 공급자 클래스는 스레드로부터 안전 하 고, 및 레지스트리 항목에 따라 설정 됩니다. 높은 수준의 다중 사용자 환경에서 성능 제공 하기 위하여 자유 스레딩 지원 하도록 하는 것이 좋습니다. 공급자에 스레드로부터 안전한을 유지 하려면 코드 제대로 차단 되었음을 확인 해야 합니다. 를 작성 하거나 데이터를 저장할 때마다 임계 영역을 사용 하 여 액세스를 차단 해야 합니다.  
  
 각 OLE DB 공급자 템플릿 개체 자체 임계 영역을 있습니다. 차단을 쉽게 하려면, 만들 각 새 클래스는 부모 클래스를 취하는 템플릿 클래스 수의 인수 이름입니다.  
  
 다음 예제에서는 코드를 차단 하는 방법을 보여 줍니다.  
  
```  
template <class T>  
class CMyObject<T> : public...  
  
HRESULT MyObject::MyMethod(void)  
{  
   T* pT = (T*)this;      // this gets the parent class   
  
// You don't need to do anything if you are only reading information  
  
// If you want to write information, do the following:  
   pT->Lock();         // engages critical section in the object  
   ...;                // write whatever information you wish  
   pT->Unlock();       // disengages the critical section  
}  
```  
  
 임계 섹션을 보호 하는 방법에 대 한 자세한 내용은 `Lock` 및 `Unlock`, 참조 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
 모든 메서드를 재정의 하는 사항도 확인 해야 합니다 (예: `Execute`)는 스레드로부터 안전 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)