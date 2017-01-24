---
title: "공급자에서 자유 스레딩 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 다중 스레드"
  - "스레딩[C++], 공급자"
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자에서 자유 스레딩 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 OLE DB 공급자 클래스는 스레드로부터 안전하고, 레지스트리 항목도 이에 따라 설정됩니다.  자유 스레드를 지원하여 다중 사용자 환경에서 성능을 향상시키는 것이 좋습니다.  공급자를 스레드로부터 안전하게 유지하려면 코드에 액세스하지 못하도록 적절히 차단해야 합니다.  데이터를 쓰거나 저장할 때마다 임계 섹션을 사용하여 액세스를 차단해야 합니다.  
  
 각 OLE DB 공급자 템플릿 개체에는 자체의 임계 섹션이 있습니다.  차단을 쉽게 하려면 사용자가 새로 만든 각 클래스가 부모 클래스 이름을 인수로 취하는 템플릿 클래스여야 합니다.  
  
 다음 예제는 코드를 차단하는 방법을 보여 줍니다.  
  
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
  
 `Lock`과 `Unlock`을 사용하여 임계 섹션을 보호하는 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)을 참조하십시오.  
  
 재정의한 메서드\(예: `Execute`\)가 모두 스레드로부터 안전한지도 확인해야 합니다.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)