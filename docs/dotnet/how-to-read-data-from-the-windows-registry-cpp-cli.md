---
title: "방법: Windows 레지스트리에서 데이터 읽기(C++/CLI) | Microsoft Docs"
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
  - "레지스트리, 읽기"
  - "Visual C++, Windows 레지스트리에서 읽기"
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows 레지스트리에서 데이터 읽기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:Microsoft.Win32.Registry.CurrentUser> 키를 사용하여 Windows 레지스트리의 데이터를 읽습니다.  우선 <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> 메서드를 사용하여 하위 키를 열거한 다음 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> 메서드를 사용하여 Identities 하위 키를 엽니다.  루트 키와 마찬가지로 각 하위 키는 <xref:Microsoft.Win32.RegistryKey> 클래스로 표현됩니다.  마지막으로 새 <xref:Microsoft.Win32.RegistryKey> 개체를 사용하여 키\/값 쌍을 열거합니다.  
  
## 예제  
  
### 코드  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## 설명  
 <xref:Microsoft.Win32.Registry> 클래스는 <xref:Microsoft.Win32.RegistryKey>의 정적 인스턴스에 대한 컨테이너에 불과합니다.  각 인스턴스는 루트 레지스트리 노드를 나타냅니다.  인스턴스는 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> 및 <xref:Microsoft.Win32.Registry.Users>입니다.  
  
 <xref:Microsoft.Win32.Registry> 클래스 내의 개체는 정적 개체인 동시에 읽기 전용 개체입니다.  또한 레지스트리 개체의 내용에 액세스하기 위해 작성된 <xref:Microsoft.Win32.RegistryKey> 클래스의 인스턴스도 읽기 전용입니다.  이 동작을 재정의하는 방법의 예제는 [방법: Windows 레지스트리에 데이터 쓰기](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)를 참조하십시오.  
  
 <xref:Microsoft.Win32.Registry> 클래스에는 <xref:Microsoft.Win32.Registry.DynData> 및 <xref:Microsoft.Win32.Registry.PerformanceData>라는 두 가지 개체가 더 있습니다.  이 두 개체는 모두 <xref:Microsoft.Win32.RegistryKey> 클래스의 인스턴스입니다.  <xref:Microsoft.Win32.Registry.DynData> 개체에는 Windows 98과 Windows Me에서만 지원되는 동적 레지스트리 정보가 들어 있습니다.  <xref:Microsoft.Win32.Registry.PerformanceData> 개체를 사용하면 Windows 성능 모니터링 시스템을 사용하는 응용 프로그램에 대한 성능 카운터 정보에 액세스할 수 있습니다.  <xref:Microsoft.Win32.Registry.PerformanceData> 노드는 레지스트리에 실제로 저장되지 않은 정보를 나타내므로 Regedit.exe를 사용하여 볼 수 없습니다.  
  
## 참고 항목  
 [방법: Windows 레지스트리에 데이터 쓰기](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)