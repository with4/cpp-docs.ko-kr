---
title: "매니페스트 리소스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56a41a7901e41f4c76fbb9fcbf5930ec97c3b866
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-resources"></a>매니페스트 리소스
매니페스트 리소스는 응용 프로그램에서 사용되는 종속성을 설명하는 XML 파일입니다. 예를 들어 Visual Studio의 MFC 마법사에서 생성되는 매니페스트 파일은 응용 프로그램이 Windows 공용 컨트롤 DLL 버전 5.0 또는 6.0 중 어느 것을 사용해야 하는지 정의합니다.  
  
```  
<description>Your app description here</description>   
<dependency>   
    <dependentAssembly>   
        <assemblyIdentity   
            type="win32"   
            name="Microsoft.Windows.Common-Controls"   
            version="6.0.0.0"   
            processorArchitecture="X86"   
            publicKeyToken="6595b64144ccf1df"   
            language="*"   
        />   
    </dependentAssembly>   
</dependency>   
```  
  
 Windows XP 또는 Windows Vista 응용 프로그램의 경우, 매니페스트 리소스는 응용 프로그램이 최신 버전(위에 나온 대로 v6.0)의 Windows 공용 컨트롤을 사용하도록 지정할 뿐만 아니라 [Syslink 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb760706)도 지원합니다.  
  
 매니페스트 리소스에 포함된 버전 및 형식 정보를 보려면 XML 뷰어 또는 Visual Studio [텍스트 편집기](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)에서 파일을 열면 됩니다. 자세한 내용은 [Visual Studio 텍스트 편집기에서 매니페스트 리소스 열기](../windows/how-to-open-a-manifest-resource.md)를 참조하세요.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은  [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)도 지원합니다.  
  
## <a name="limitations"></a>제한 사항  
 모듈별로 매니페스트 리소스를 하나만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤](../mfc/controls-mfc.md)   
 [리소스 파일 작업](../windows/working-with-resource-files.md)