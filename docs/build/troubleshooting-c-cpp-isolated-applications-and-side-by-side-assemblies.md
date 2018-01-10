---
title: "격리 된 응용 프로그램 및 side-by-side-어셈블리 C/c + + 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- troubleshooting side-by-side assemblies
- troubleshooting isolated applications
- troubleshooting Visual C++
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3ea32a33a3194282657999712effbad0e334bea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="troubleshooting-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 문제 해결
종속 라이브러리를 찾을 수 없는 경우 C/C++ 응용 프로그램을 로드하지 못할 수 있습니다. 이 문서에서는 C/C++ 응용 프로그램을 로드하지 못하는 몇 가지 일반적인 이유에 대해 설명하고 문제를 해결할 수 있는 단계를 제안합니다.  
  
 병렬 어셈블리에 대해 종속성을 지정하는 매니페스트가 있어 응용 프로그램을 로드하지 못하는 경우 어셈블리가 실행 파일과 동일한 폴더나 %WINDIR%\WinSxS\ 폴더의 네이티브 어셈블리 캐시에 전용 어셈블리로 설치되어 있지 않으면 앱을 실행하려는 Windows 버전에 따라 다음 오류 메시지 중 하나가 표시될 수 있습니다.  
  
-   응용 프로그램을 제대로 초기화하지 못했습니다(0xc0000135).  
  
-   응용 프로그램 구성이 잘못되어 응용 프로그램을 시작하지 못했습니다. 응용 프로그램을 다시 설치하면 이 문제가 해결될 수 있습니다.  
  
-   시스템이 지정된 프로그램을 실행할 수 없습니다.  
  
 응용 프로그램에 매니페스트가 없고 일반적인 검색 위치에서 Windows가 찾을 수 없는 DLL에 응용 프로그램이 종속되어 있으면 다음과 유사한 오류 메시지가 표시될 수 있습니다.  
  
-   이 응용 프로그램 때문에 시작 하지 못했습니다 *필요한 DLL* 찾을 수 없습니다. 이 문제를 해결하려면 응용 프로그램을 다시 설치하세요.  
  
 응용 프로그램이 Visual Studio가 없는 컴퓨터에 배포된 경우 충돌하여 이전과 유사한 오류 메시지가 표시되면 다음 사항을 확인하세요.  
  
1.  에 설명 된 단계에 따라 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)합니다. Dependency Walker에서 응용 프로그램이나 DLL에 대한 대부분의 종속성을 표시할 수 있습니다. 일부 DLL이 누락된 경우 응용 프로그램을 실행하려는 컴퓨터에 설치합니다.  
  
2.  운영 체제 로더는 응용 프로그램 매니페스트를 사용하여 응용 프로그램이 종속된 어셈블리를 로드합니다. 매니페스트는 리소스로 이진 파일에 포함하거나 별도의 파일로 응용 프로그램 폴더에 설치할 수 있습니다. 매니페스트가 이진 파일에 포함되어 있는지 확인하려면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 이진 파일을 열고 리소스 목록에서 RT_MANIFEST를 찾습니다. 포함된 된 매니페스트를 찾을 수 없는 경우 다음과 같이 < binary_name >에서 명명 된 파일에 대 한 응용 프로그램 폴더에서 찾습니다. \<확장 >.manifest입니다.  
  
3.  응용 프로그램이 side-by-side 어셈블리에 종속된 경우 매니페스트가 없으면 링커에서 프로젝트에 대한 매니페스트를 생성하도록 해야 합니다. 링커 옵션을 확인 **매니페스트 생성** 에 **프로젝트 속성** 프로젝트에 대 한 대화 상자.  
  
4.  매니페스트가 이진 파일에 포함된 경우 RT_MANIFEST의 ID가 이 형식의 이진 파일에 적합한지 확인합니다. 사용 하는 리소스 ID에 대 한 자세한 내용은 참조 하십시오. [Side-by-side-어셈블리 (Windows)를 리소스로 사용](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx)합니다. 매니페스트가 별도의 파일에 있는 경우 XML 편집기나 텍스트 편집기에서 엽니다. 매니페스트 및 배포에 대 한 규칙에 대 한 자세한 내용은 참조 [매니페스트](http://msdn.microsoft.com/library/aa375365)합니다.  
  
    > [!NOTE]
    >  포함된 매니페스트와 별도의 매니페스트 파일이 둘 다 있는 경우 운영 체제 로더는 포함된 매니페스트를 사용하고 별도의 파일을 무시합니다. 그러나 Windows XP에서는 반대로 별도의 매니페스트 파일이 사용되고 포함된 매니페스트가 무시됩니다.  
  
5.  DLL이 `LoadLibrary` 호출을 통해 로드될 경우 외부 매니페스트가 무시되므로 모든 DLL에 매니페스트를 포함하는 것이 좋습니다. 자세한 내용은 참조 [어셈블리 매니페스트](http://msdn.microsoft.com/library/aa374219)합니다.  
  
6.  매니페스트에 열거되는 모든 어셈블리가 컴퓨터에 올바르게 설치되어 있는지 확인합니다. 각 어셈블리는 이름, 버전 번호 및 프로세서 아키텍처별로 매니페스트에 지정됩니다. 응용 프로그램-side-by-side 어셈블리에 의존 하는 경우 이러한 어셈블리 설치 되어 있는지 확인 올바르게 컴퓨터에 운영 체제 로더를 찾을 수 있도록에 설명 된 대로 [어셈블리 검색 시퀀스](http://msdn.microsoft.com/library/aa374224)합니다. 64비트 어셈블리는 32비트 프로세스에서 로드할 수 없으며 32비트 운영 체제에서 실행할 수 없습니다.  
  
## <a name="example"></a>예  
 Visual c + +를 사용 하 여 만들어지는 appl.exe 응용 프로그램이 있다고 가정 합니다. 응용 프로그램 매니페스트는 ID가 1인 이진 리소스 RT_MANIFEST로 appl.exe에 포함되거나 별도의 파일 appl.exe.manifest로 저장됩니다. 이 매니페스트의 콘텐츠는 다음과 같습니다.  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 운영 체제 로더에게 이 매니페스트는 appl.exe가 32비트 x86 프로세서 아키텍처용으로 빌드된 Fabrikam.SxS.Library, 버전 2.0.20121.0에 종속된다는 의미입니다. 종속 side-by-side 어셈블리는 공유 어셈블리나 전용 어셈블리로 설치할 수 있습니다.  
  
 공유 어셈블리에 대한 어셈블리 매니페스트는 %WINDIR%\WinSxS\Manifests\ 폴더에 설치됩니다. 이 매니페스트는 어셈블리를 식별하고 해당 콘텐츠 즉, 어셈블리의 일부인 DLL을 나열합니다.  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 Side-by-side-어셈블리를 사용할 수도 [게시자 구성 파일](http://msdn.microsoft.com/library/aa375682)-정책 파일이 라고도-전역으로 리디렉션할 동일한의 다른 버전 대신 side-by-side-어셈블리의 버전을 사용 하는 응용 프로그램 및 어셈블리 어셈블리입니다. %WINDIR%\WinSxS\Policies\ 폴더에서 공유 어셈블리에 대한 정책을 확인할 수 있습니다. 다음은 예제 정책 파일입니다.  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 이 정책 파일은 이 어셈블리의 버전 2.0.10000.0을 요청하는 응용 프로그램이나 어셈블리에서 시스템에 설치되어 있는 현재 버전인 2.0.20121.0을 대신 사용하도록 지정합니다. 응용 프로그램 매니페스트에 언급된 어셈블리의 버전이 정책 파일에 지정된 경우 로더는 %WINDIR%\WinSxS\ 폴더에서 매니페스트에 지정된 이 어셈블리의 버전을 찾고, 이 버전이 설치되지 않은 경우 로드에 실패합니다. 또한 어셈블리 버전 2.0.20121.0이 설치되지 않은 경우 어셈블리 버전 2.0.10000.0을 요청하는 응용 프로그램 로드에 실패합니다.  
  
 그러나 어셈블리를 설치된 응용 프로그램 폴더에 전용 side-by-side 어셈블리로 설치할 수도 있습니다. 운영 체제에서 어셈블리를 공유 어셈블리로 찾지 못하면 다음 순서에 따라 전용 어셈블리로 찾습니다.  
  
1.  이름이 있는 매니페스트 파일에 대 한 응용 프로그램 폴더를 확인 \<assemblyName >.manifest입니다. 이 예제에서 로더는 appl.exe가 포함된 폴더에서 Fabrikam.SxS.Library.manifest를 찾으려고 합니다. 매니페스트를 찾으면 로더는 응용 프로그램 폴더에서 어셈블리를 로드합니다. 어셈블리가 없으면 로드에 실패합니다.  
  
2.  열려고는 \\< assemblyName\>\ appl.exe를 포함 하는 폴더의 폴더 및 if \\< assemblyName\>\ 존재 이름이 있는 매니페스트 파일을 로드 하려고 \<assemblyName > 합니다. 이 폴더에서 매니페스트 합니다. 매니페스트를 찾으면 로더에서 어셈블리를 로드는 \\< assemblyName\>\ 폴더입니다. 어셈블리가 없으면 로드에 실패합니다.  
  
 로더에서 종속 어셈블리를 검색 하는 방법에 대 한 자세한 내용은 참조 [어셈블리 검색 시퀀스](http://msdn.microsoft.com/library/aa374224)합니다. 로더에서 종속 어셈블리를 전용 어셈블리로 찾지 못하면 로드에 실패하고 "시스템이 지정된 프로그램을 실행할 수 없습니다."라는 메시지가 표시됩니다. 이 오류를 해결하려면 종속 어셈블리 및 해당 어셈블리의 일부인 DLL이 전용 또는 공유 어셈블리로 컴퓨터에 설치되어 있는지 확인하세요.  
  
## <a name="see-also"></a>참고 항목  
 [격리 된 응용 프로그램 및 side-by-side-어셈블리의 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)