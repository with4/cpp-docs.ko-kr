---
title: "-CLRUNMANAGEDCODECHECK (Supressunmanagedcodesecurityattribute 추가) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRUNMANAGEDCODECHECK
dev_langs: C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0ac6b7c2c0ba9ea14a2ddd9c227143ec71e2b93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK(SupressUnmanagedCodeSecurityAttribute 추가)
**/CLRUNMANAGEDCODECHECK** 링커 적용 되는지 여부를 지정 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 링커 생성 `PInvoke` 관리 코드에서 네이티브 Dll로 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>설명  
 SuppressUnmanagedCodeSecurityAttribute는 링커 생성 링커 기본적으로 적용 `PInvoke` 호출 합니다. 때 **/CLRUNMANAGEDCODECHECK** 가 적용 된 경우 SuppressUnmanagedCodeSecurityAttribute가 적용 되지 않았습니다.  
  
 링커로 컴파일된 개체에 특성 추가 **/clr** 또는 **/clr: pure**합니다. 링커 생성 하지 않습니다 `PInvoke` 로 컴파일한 개체에서 호출 **/clr: safe**합니다. 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 A `PInvoke` 관리 되는 호출자에 대 한 참조를 충족 하기 위해 관리 되는 기호를 찾을 수 없지만 해당 참조를 충족 하기 위해 네이티브 기호 찾을 수 있는 경우 링커에 의해 호출을 생성 합니다. 에 대 한 자세한 내용은 `PInvoke`, 참조 [관리 코드에서 네이티브 함수 호출](../../dotnet/calling-native-functions-from-managed-code.md)합니다.  
  
 사용 하는 경우 유의 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 코드를 명시적으로 설정 해야 **/CLRUNMANAGEDCODECHECK**합니다. 이미지 SuppressUnmanagedCodeSecurity와 AllowPartiallyTrustedCallers 특성을 포함 하는 경우 잠재적 보안 취약점입니다.  
  
 참조 [보안 코딩 지침 비관리 코드에 대 한](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) SuppressUnmanagedCodeSecurityAttribute 사용의 의미에 대 한 자세한 내용은 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **고급** 속성 페이지.  
  
5.  수정 된 **CLR 비관리 코드 검사** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)