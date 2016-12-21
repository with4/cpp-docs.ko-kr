---
title: "방법: Windows 성능 카운터 읽기(C++/CLI) | Microsoft Docs"
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
  - "카운터, Windows 성능 카운터 읽기"
  - "성능"
  - "성능 카운터"
  - "성능 카운터, Windows 성능 카운터 읽기"
  - "성능 모니터링"
  - "성능 모니터링, Windows 성능 카운터"
  - "성능, 카운터"
ms.assetid: 9e1c836c-cb0f-4f37-9a93-3dca6412d6b1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows 성능 카운터 읽기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일부 응용 프로그램과 Windows 하위 시스템에서는 Windows 성능 시스템을 통해 성능 데이터를 노출합니다.  <xref:System.Diagnostics?displayProperty=fullName> 네임스페이스에 있는 <xref:System.Diagnostics.PerformanceCounterCategory> 및 <xref:System.Diagnostics.PerformanceCounter> 클래스를 사용하면 이러한 카운터에 액세스할 수 있습니다.  
  
 다음 코드 예제에서는 프로세서가 사용 중인 시간을 백분율로 나타내기 위해 Windows에서 업데이트된 카운터를 검색하고 표시하는 데 이러한 클래스를 사용합니다.  
  
> [!NOTE]
>  이 예제에서는 Windows Vista를 실행하기 위한 관리자 권한이 필요합니다.  
  
## 예제  
  
```  
// processor_timer.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Diagnostics;  
using namespace System::Timers;  
  
ref struct TimerObject  
{  
public:  
   static String^ m_instanceName;  
   static PerformanceCounter^ m_theCounter;  
  
public:  
   static void OnTimer(Object^ source, ElapsedEventArgs^ e)  
   {  
      try   
      {  
         Console::WriteLine("CPU time used: {0,6} ",  
          m_theCounter->NextValue( ).ToString("f"));  
      }   
      catch(Exception^ e)  
      {  
         if (dynamic_cast<InvalidOperationException^>(e))  
         {  
            Console::WriteLine("Instance '{0}' does not exist",  
                  m_instanceName);  
            return;  
         }  
         else  
         {  
            Console::WriteLine("Unknown exception... ('q' to quit)");  
            return;  
         }  
      }  
   }  
};  
  
int main()  
{  
   String^ objectName = "Processor";  
   String^ counterName = "% Processor Time";  
   String^ instanceName = "_Total";  
  
   try  
   {  
      if ( !PerformanceCounterCategory::Exists(objectName) )  
      {  
         Console::WriteLine("Object {0} does not exist", objectName);  
         return -1;  
      }  
   }  
   catch (UnauthorizedAccessException ^ex)  
   {  
      Console::WriteLine("You are not authorized to access this information.");  
      Console::Write("If you are using Windows Vista, run the application with ");  
      Console::WriteLine("administrative privileges.");  
      Console::WriteLine(ex->Message);  
      return -1;  
   }  
  
   if ( !PerformanceCounterCategory::CounterExists(  
          counterName, objectName) )  
   {  
      Console::WriteLine("Counter {0} does not exist", counterName);  
      return -1;  
   }  
  
   TimerObject::m_instanceName = instanceName;  
   TimerObject::m_theCounter = gcnew PerformanceCounter(  
          objectName, counterName, instanceName);  
  
   System::Timers::Timer^ aTimer = gcnew System::Timers::Timer();  
   aTimer->Elapsed += gcnew ElapsedEventHandler(&TimerObject::OnTimer);  
   aTimer->Interval = 1000;  
   aTimer->Enabled = true;  
   aTimer->AutoReset = true;  
  
   Console::WriteLine("reporting CPU usage for the next 10 seconds");  
   Thread::Sleep(10000);  
   return 0;  
}  
```  
  
## 참고 항목  
 [Introduction to Monitoring Performance](http://msdn.microsoft.com/ko-kr/d40f10b9-e2b7-4ec8-a9b3-706929e5bf35)   
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)