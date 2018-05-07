---
title: 강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d7ae911d2572a35ee8dbb21d5484b4679b64c4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)
이 항목 라고도 어셈블리에 강력한 이름을 지정 하면 어셈블리를 서명할 수 방법을 설명 합니다.  
  
## <a name="remarks"></a>설명  
 Visual c + +를 사용할 경우 서명 된 어셈블리에 대 한 CLR 특성에 관련 된 문제를 방지 하기 위해 어셈블리에 서명할 링커 옵션을 사용 합니다.  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 특성을 사용 하지 않는 이유는 키 이름을 파일 이름 기밀 정보를 포함 하는 경우 보안 위험이 발생할 수 있는 어셈블리 메타 데이터에 표시 된다는 사실에 입각을 포함 됩니다. 또한 Visual c + + 개발 환경에서 사용 하는 빌드 프로세스는 CLR 특성을 어셈블리에 강력한 이름을 사용 하 고 어셈블리에서 같은 mt.exe 후 처리 도구를 실행 하는 경우 어셈블리가 서명 되는 키를 무효화 됩니다.  
  
 명령줄에서 빌드, 링커 옵션을 사용 하 여 어셈블리를 서명 하 고 다음 (예: mt.exe) 후 처리 도구를 실행 하는 경우에 다시 sn.exe 사용 하 여 어셈블리를 서명 해야 합니다. 또는 수 및 어셈블리 서명을 연기 빌드하고 완료 후 처리 도구를 실행 한 후 서명 합니다.  
  
 Sn.exe를 명시적으로 호출 하 여 어셈블리를 성공적으로 서명할 수는 개발 환경에서 빌드하는 경우 서명 특성을 사용 하는 경우 ([Sn.exe (강력한 이름 도구)](/dotnet/framework/tools/sn-exe-strong-name-tool))는 빌드 후 이벤트에 있습니다. 자세한 내용은 참조 [빌드 이벤트 지정](../ide/specifying-build-events.md)합니다. 특성 및 링커 옵션을 사용 하는 빌드 후 이벤트를 사용 하는 경우 빌드 시간이 적을 수 있습니다.  
  
 어셈블리 서명 다음 링커 옵션을 지원 합니다.  
  
-   [/DELAYSIGN(어셈블리에 부분적으로 서명)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER(어셈블리에 서명할 키 컨테이너 지정)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 강력한 이름의 어셈블리에 대 한 자세한 내용은 참조 하십시오. [and using strong-named Assemblies](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)