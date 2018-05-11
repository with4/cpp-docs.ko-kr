---
title: lock::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- operator bool
- msclr.lock.operator bool
- lock.operator bool
- msclr::lock::operator bool
- lock::operator bool
dev_langs:
- C++
helpviewer_keywords:
- lock::operator bool
ms.assetid: 007f0372-f812-4f1e-ba43-2584bd96eb11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a68093ce1bca76d685a6809b8c2a612acaca9d7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="lockoperator-bool"></a>lock::operator bool
사용 하 여에 대 한 연산자 `lock` 조건식에서입니다.  
  
## <a name="syntax"></a>구문  
  
```  
operator bool();  
```  
  
## <a name="return-value"></a>반환 값  
 `true` 잠금이 유지 되는 경우 `false` 그렇지 않은 경우.  
  
## <a name="remarks"></a>설명  
 이 연산자를 실제로 변환 `_detail_class::_safe_bool` 보다 더 안전 하 게 되 `bool` 정수 계열 형식으로 변환할 수 없기 때문입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 여러 스레드 간에 클래스의 단일 인스턴스를 사용 합니다.  클래스를 사용 하 여 잠금을 자체에서 내부 데이터에 대 한 액세스가 각 스레드에 대해 일관적인 지 확인 합니다.  기본 응용 프로그램 스레드는 주기적으로 확인 하는 경우 모든 작업자 스레드 여전히 존재 하며, 해당 작업을 완료 될 때까지 모든 작업자 스레드가 끝나기를 대기 하는 클래스의 동일한 인스턴스에 잠금을 사용 합니다.  
  
```  
// msl_lock_op_bool.cpp  
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
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't  
      if (l) { // use bool operator to check for lock  
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
 [lock::is_locked](../dotnet/lock-is-locked.md)