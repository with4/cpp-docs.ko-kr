---
title: "방법: 파일 시스템 변경 사항 모니터링(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "이벤트[C++], 모니터링"
  - "예제[C++], 파일 시스템 변경 사항 모니터링"
  - "파일 시스템 이벤트[C++]"
  - "FileSystemWatcher 클래스, 예제"
  - "파일 시스템 이벤트 모니터링"
ms.assetid: 207a3069-e63d-417e-8b56-00ab44f29c52
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 파일 시스템 변경 사항 모니터링(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.IO.FileSystemWatcher>를 사용하여 파일이 생성, 변경 또는 삭제되거나 피일의 이름이 변경될 때 발생하는 이벤트에 대해 등록합니다.  디렉터리에서 주기적으로 파일 변경 내용을 폴링하는 대신 <xref:System.IO.FileSystemWatcher> 클래스를 사용하여 변경 내용이 발견되면 이벤트가 발생하도록 할 수 있습니다.  
  
## 예제  
  
```  
// monitor_fs.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::IO;  
  
ref class FSEventHandler  
{  
public:  
    void OnChanged (Object^ source, FileSystemEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} {1}",   
               e->FullPath, e->ChangeType);  
    }  
    void OnRenamed(Object^ source, RenamedEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} renamed to {1}",   
                e->OldFullPath, e->FullPath);  
    }  
};  
  
int main()  
{  
   array<String^>^ args = Environment::GetCommandLineArgs();  
  
   if(args->Length < 2)  
   {  
      Console::WriteLine("Usage: Watcher.exe <directory>");  
      return -1;  
   }  
  
   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );  
   fsWatcher->Path = args[1];  
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>   
              (NotifyFilters::FileName |   
               NotifyFilters::Attributes |   
               NotifyFilters::LastAccess |   
               NotifyFilters::LastWrite |   
               NotifyFilters::Security |   
               NotifyFilters::Size );  
  
    FSEventHandler^ handler = gcnew FSEventHandler();   
    fsWatcher->Changed += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Created += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Deleted += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Renamed += gcnew RenamedEventHandler(   
            handler, &FSEventHandler::OnRenamed);  
  
    fsWatcher->EnableRaisingEvents = true;  
  
    Console::WriteLine("Press Enter to quit the sample.");  
    Console::ReadLine( );  
}  
```  
  
## 참고 항목  
 [System.IO 네임스페이스](https://msdn.microsoft.com/en-us/library/system.io.aspx)   
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)