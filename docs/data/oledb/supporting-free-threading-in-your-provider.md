---
title: 공급자에서 자유 스레딩 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 17750a61675f9b208be69b86ec7b044b6b19f1bb
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336679"
---
# <a name="supporting-free-threading-in-your-provider"></a>공급자에서 자유 스레딩 지원
모든 OLE DB 공급자 클래스는 스레드로부터 안전 하 고 레지스트리 항목에 따라 설정 됩니다. 다중 사용자 환경에서 성능 수준을 높이기 위해 자유 스레딩 지원 하도록 하는 것이 좋습니다. 공급자 스레드 안전 유지를 위해 코드를 제대로 차단 되는 확인 해야 합니다. 를 작성 하거나 데이터를 저장할 때마다 중요 섹션을 사용 하 여 액세스를 차단 해야 합니다.  
  
 각 OLE DB 공급자 템플릿 개체에 중요 한 고유한 섹션이 있습니다. 차단을 쉽게 하려면, 각 새 클래스를 만들면 해야 부모 과목을 수강 하는 템플릿 클래스를 인수로 이름입니다.  
  
 다음 예제에서는 코드를 차단 하는 방법을 보여 줍니다.  
  
```cpp  
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
  
 임계 섹션을 보호 하는 방법에 대 한 자세한 내용은 `Lock` 및 `Unlock`를 참조 하세요 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
 메서드를 재정의 하는 확인 해야 합니다 (같은 `Execute`)는 스레드로부터 안전 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)