---
title: "방법: Windows 레지스트리에 데이터 쓰기(C++/CLI) | Microsoft Docs"
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
  - "레지스트리, 쓰기"
  - "Visual C++, Windows 레지스트리에 쓰기"
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows 레지스트리에 데이터 쓰기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:Microsoft.Win32.Registry.CurrentUser> 키를 사용하여 **Software** 키에 상응하는 <xref:Microsoft.Win32.RegistryKey> 클래스의 쓰기 가능한 인스턴스를 만듭니다.  그런 다음 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> 메서드를 사용하여 새 키를 만들고 키\/값 쌍을 추가합니다.  
  
## 예제  
  
### 코드  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## 설명  
 .NET Framework를 사용하면 <xref:Microsoft.Win32.Registry> 및 [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) 클래스를 통해 레지스트리에 액세스할 수 있습니다. 이 두 클래스는 모두 <xref:Microsoft.Win32> 네임스페이스에 정의되어 있습니다.  **Registry** 클래스는 <xref:Microsoft.Win32.RegistryKey> 클래스의 정적 인스턴스에 대한 컨테이너입니다.  각 인스턴스는 루트 레지스트리 노드를 나타냅니다.  인스턴스는 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> 및 <xref:Microsoft.Win32.Registry.Users>입니다.  
  
## 참고 항목  
 [방법: Windows 레지스트리에서 데이터 읽기](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)