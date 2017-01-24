---
title: "WRL 클래스 라이브러리 프로젝트 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WRL 클래스 라이브러리 프로젝트 템플릿
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio를 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) 프로젝트를 읽기 위해 사용할 경우, WIRL 클래스 라이브러리 프로젝트 탬플릿을 다운로드 함으로써 대폭적으로 단순화시킬 수 있습니다.  
  
> [!NOTE]
>  기존 프로젝트의 프로젝트 설정을 수동으로 업데이트 해야 할 경우, [Dll \(C \+ \+ \/cli CX\)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx) 참조합니다.  
  
## WRL 프로젝트 탬플릿을 다운로드합니다.  
 Visual Studio는 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 프로젝트에 대한 탬플릿을 제공하지 않습니다.  이것은 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 사용하는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에 대하여 기본 클래스 라이브러리를 만드는 프로젝트 탬플릿을 어떻게 다운로드 하는지입니다.  
  
#### WRL 프로젝트 탬플릿을 다운로드합니다.  
  
1.  메뉴 모음에서 **파일**, **새 프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화상자의 왼쪽 창에서, **온라인** 을 선택하고, 그때, **탬플릿** 을 선택합니다.  
  
3.  오른쪽 상단 코너에서 **검색 온라인 탬플릿** 상자에서 형식 `WRL 클래스 라이브러리`.  서식 파일 검색 결과에 나타나면, **확인** 단추를 선택합니다.  
  
4.  **다운로드 및 설치** 대화상자에서, 라이센스에 동의한다면, **설치** 단추를 선택합니다.  
  
5.  탬플릿을 설치한 후, **파일** 과 **새 프로젝트** 를 선택함으로써 프로젝트를 만들고, 그 때 `WRLClassLibrary` 탬플릿을 선택합니다.  프로젝트는 DLL을 만듭니다.  
  
## 프로젝트 템플릿을 사용하는 예제  
 이 탬플릿을 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성요소를 만들기 위해 사용하는 예제인 [연습: 기본 Windows Runtime 구성 요소 만들기](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) 를 읽습니다.  
  
## 프로젝트 템플릿 제공  
 프로젝트 템플릿 제공:  
  
-   .idl 파일 클래스 구현에 기본 인터페이스에 대한 MIDL 특성을 선언합니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   클래스 구현을 정의 하는.cpp 파일입니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md) 기본 클래스는 모듈에서 모든 개체의 전역참조를 관리하는 것을 돕고, [IUnknown](http://msdn.microsoft.com/ko-kr/33f1d79a-33fc-4ce5-a372-e08bda378332) 및 [IInspectable](http://msdn.microsoft.com/ko-kr/0657e51f-d4c0-46c6-927d-b01e54b6846c) 인터페이스의 메서드를 선언합니다.  [InspectableClass](../windows/inspectableclass-macro.md) 매크로는 `IUnknown` 및 `IInspectable` 를 구현합니다.  [ActivatableClass](../windows/activatableclass-macros.md) 매크로는 클래스의 인스턴스를 생성하는 클래스 팩터리를 만듭니다.  
  
-   라이브러리를 정의 하는 module.cpp 라는 파일을 내보내는 `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory`, 및 `DllGetClassObject`.  
  
## 참고 항목  
 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)