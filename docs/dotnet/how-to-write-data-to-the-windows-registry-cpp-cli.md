---
title: '방법: Windows 레지스트리에 데이터 쓰기 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 304bc224be8776c9793af07283c6a5697a4e49eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-data-to-the-windows-registry-ccli"></a>방법: Windows 레지스트리에 데이터 쓰기(C++/CLI)
다음 코드 예제에서는 <xref:Microsoft.Win32.Registry.CurrentUser> 의 쓰기 가능한 인스턴스를 만드는 키는 <xref:Microsoft.Win32.RegistryKey> 클래스에 해당 하는 **소프트웨어** 키입니다. <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> 메서드는 다음 새 키를 만들고 키/값 쌍을 추가 하는 데 사용 됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
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
  
## <a name="remarks"></a>설명  
 .NET Framework를 사용 하 여 사용 하 여 레지스트리를 액세스 하는 <xref:Microsoft.Win32.Registry> 및 [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) 에 정의 된 클래스는 둘 다는 <xref:Microsoft.Win32> 네임 스페이스입니다. **레지스트리** 클래스는의 정적 인스턴스에 대 한 컨테이너는 <xref:Microsoft.Win32.RegistryKey> 클래스입니다. 각 인스턴스는 루트 레지스트리 노드를 나타냅니다. 인스턴스는 <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, 및 <xref:Microsoft.Win32.Registry.Users>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows 레지스트리에서 데이터 읽기 (C + + /cli CLI)](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)