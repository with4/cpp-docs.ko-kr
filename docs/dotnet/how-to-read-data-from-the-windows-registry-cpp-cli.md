---
title: '방법: Windows 레지스트리에서 데이터 읽기 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, reading from Windows Registry
- registry, reading
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87c882bcf2a7900e1f95ea968407c159333c6cb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-data-from-the-windows-registry-ccli"></a>방법: Windows 레지스트리에서 데이터 읽기(C++/CLI)
다음 코드 예제에서는 <xref:Microsoft.Win32.Registry.CurrentUser> 데이터를 읽을 때 Windows 레지스트리에서 키입니다. 첫째, 하위 키를 사용 하 여 열거 되는 <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> 메서드 및 Identities 하위 키를 사용 하 여을 열릴는 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> 메서드. 루트 키와 마찬가지로 각 하위 키로 표시 됩니다는 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. 마지막으로, 새 <xref:Microsoft.Win32.RegistryKey> 개체 키/값 쌍을 열거 하는 데 사용 됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
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
  
## <a name="remarks"></a>설명  
 <xref:Microsoft.Win32.Registry> 클래스는 컨테이너의 정적 인스턴스에 대 한 단지 <xref:Microsoft.Win32.RegistryKey>합니다. 각 인스턴스는 루트 레지스트리 노드를 나타냅니다. 인스턴스는 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, 및 <xref:Microsoft.Win32.Registry.Users>합니다.  
  
 에 추가 되 고 정적 내의 개체에는 <xref:Microsoft.Win32.Registry> 클래스는 읽기 전용입니다. 또한, 인스턴스의 <xref:Microsoft.Win32.RegistryKey> 레지스트리의 내용에 액세스 하기 위해 만든 클래스 개체는 읽기 전용도 합니다. 이 동작을 재정의 하는 방법의 예제를 보려면 [하는 방법: Windows 레지스트리에 데이터 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)합니다.  
  
 두 가지 추가 개체에는 <xref:Microsoft.Win32.Registry> 클래스: <xref:Microsoft.Win32.Registry.DynData> 및 <xref:Microsoft.Win32.Registry.PerformanceData>합니다. 둘 다의 인스턴스는 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. <xref:Microsoft.Win32.Registry.DynData> 에서만 Windows 98 및 Windows me에서 지원 되는 동적 레지스트리 정보를 포함 하는 개체 <xref:Microsoft.Win32.Registry.PerformanceData> Windows 성능 모니터링 시스템을 사용 하는 응용 프로그램에 대 한 성능 카운터 정보에 액세스 하려면 개체를 사용할 수 있습니다. <xref:Microsoft.Win32.Registry.PerformanceData> 노드는 실제로 레지스트리에 저장 되지 않으며, 따라서 볼 수 없습니다 Regedit.exe를 사용 하는 정보를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows 레지스트리에 데이터 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)