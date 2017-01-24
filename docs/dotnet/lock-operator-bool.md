---
title: "lock::operator bool | Microsoft Docs"
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
  - "operator bool"
  - "msclr.lock.operator bool"
  - "lock.operator bool"
  - "msclr::lock::operator bool"
  - "lock::operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::operator bool"
ms.assetid: 007f0372-f812-4f1e-ba43-2584bd96eb11
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

연산자를 사용하여 `lock` 조건식에서 입니다.  
  
## 구문  
  
```  
operator bool();  
```  
  
## 반환 값  
 `true`잠금이 유지 되는 경우  `false` .  
  
## 설명  
 이 연산자를 실제로 변환  `_detail_class::_safe_bool`  은 보다 안전 하 게  `bool`  정수 계열 형식으로 변환할 수 없습니다.  
  
## 예제  
 이 예제에서는 여러 스레드에서 클래스의 단일 인스턴스를 사용합니다.  클래스 자체에 lock을 사용 하 여 내부 데이터에 대 한 액세스는 각 스레드에 대해 일관성이 확인합니다.  주 응용 프로그램 스레드 클래스의 동일한 인스턴스에 lock을 사용 하 여 주기적으로 확인 하 고 대기까지 모든 작업자 스레드를 종료 하려면 해당 작업을 완료 한 모든 작업자 스레드가 여전히 존재합니다.  
  
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
  
  **3 스레드 0 \= 카운터**  
**3 스레드 10 \= 카운터**  
**5 스레드 0 \= 카운터**  
**5 스레드 10 \= 카운터**  
**7 스레드 0 \= 카운터**  
**7 스레드 10 \= 카운터**  
**4 스레드 0 \= 카운터**  
**4 스레드 10 \= 카운터**  
**6 스레드 0 \= 카운터**  
**6 스레드 10 \= 카운터**  
**모든 스레드를 완료 합니다.**   
## 요구 사항  
 **헤더 파일** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [lock 멤버](../dotnet/lock-members.md)   
 [lock::is\_locked](../dotnet/lock-is-locked.md)