---
title: 프로그램 내에서 버전 정보 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8913e0dc33da1de2f240305ff19f5250e38b180
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856273"
---
# <a name="accessing-version-information-from-within-your-program"></a>프로그램 내에서 버전 정보 액세스
### <a name="to-access-version-information-from-within-your-program"></a>프로그램 내에서 버전 정보에 액세스하려면  
  
1.  프로그램 내에서 버전 정보에 액세스하려는 경우 [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) 함수 및 [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx) 함수를 사용합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [버전 정보 편집기](../windows/version-information-editor.md)   
 [버전 정보 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

