---
title: lock::try_acquire | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- try_acquire
- lock.try_acquire
- msclr.lock.try_acquire
- lock::try_acquire
- msclr::lock::try_acquire
dev_langs:
- C++
helpviewer_keywords:
- lock::try_acquire
ms.assetid: ef0649a9-e611-4495-84bd-2784533221d9
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da2372f513d9799cfddbebeefa7e9160d1a6b135
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="locktryacquire"></a>lock::try_acquire
지정 된 시간 동안 대기 하 고 반환 하는 개체에 대 한 잠금을 획득 한 `bool` 예외를 throw 하는 대신 취득의 성공 여부를 보고 하기 위해 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool try_acquire(  
   int _timeout_ms  
);  
bool try_acquire(  
   System::TimeSpan _timeout  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_timeout`  
 제한 시간 값 (밀리초) 또는 <xref:System.TimeSpan>합니다.  
  
## <a name="return-value"></a>반환 값  
 `true`잠금을 획득 하는 경우 `false` 그렇지 않은 경우.  
  
## <a name="remarks"></a>설명  
 잠금을 이미 가져온 경우이 함수는 아무 작업도 수행 하지 않습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스를 사용 하 여 잠금을 자체에서 내부 데이터에 대 한 액세스가 각 스레드에 대해 일관적인 지 확인 합니다.  기본 응용 프로그램 스레드는 주기적으로 확인 하는 경우 모든 작업자 스레드 여전히 존재 하며, 해당 작업을 완료 될 때까지 모든 작업자 스레드가 끝나기를 대기 하는 클래스의 동일한 인스턴스에 잠금을 사용 합니다.  
  
```  
// msl_lock_try_acquire.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
```Output  
In thread 3, Counter = 0  
In thread 3, Counter = 10  
In thread 5, Counter = 0  
In thread 5, Counter = 10  
In thread 7, Counter = 0  
In thread 7, Counter = 10  
In thread 4, Counter = 0  
In thread 4, Counter = 10  
In thread 6, Counter = 0  
In thread 6, Counter = 10  
All threads completed.  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>참고 항목  
 [lock 멤버](../dotnet/lock-members.md)   
 [lock::acquire](../dotnet/lock-acquire.md)