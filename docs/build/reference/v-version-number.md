---
title: "/V(버전 번호) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/v"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/V 컴파일러 옵션[C++]"
  - "버전 문자열 포함"
  - "V 컴파일러 옵션[C++]"
  - "-V 컴파일러 옵션[C++]"
  - "버전 번호, .obj 지정"
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /V(버전 번호)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

텍스트 문자열을 .obj 파일에 포함합니다.  사용되지 않습니다.  
  
## 구문  
  
```  
/Vstring  
```  
  
## 인수  
 `string`  
 obj 파일에 포함될 버전 번호나 저작권 표시를 지정하는 문자열  
  
## 설명  
 이 문자열을 사용하여 .obj 파일에 버전 번호나 저작권 정보를 표시할 수 있습니다.  공백이나 탭 문자를 문자열의 일부로 사용하는 경우에는 큰따옴표\("\)로 묶어야 합니다.  큰따옴표가 문자열의 일부로 사용되는 경우에는 백슬래시\(\\\)를 모든 큰따옴표 앞에 넣어야 합니다.  **\/V**와 `string` 사이에는 공백을 넣어도 되고 넣지 않아도 됩니다.  
  
 사용자는 또한 [주석](../../preprocessor/comment-c-cpp.md)를 컴파일러 주석 형식 인수와 함께 사용하여 컴파일러의 이름과 버전 번호를 .obj 파일에 포함할 수 있습니다.  
  
 **\/V**는 더 이상 사용되지 않습니다. **\/V**는 주로 가상 장치 드라이버\(VxDs\) 빌드를 지원하는 데 사용되었으나, [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 도구 집합에서는 VxDs 빌드를 더 이상 지원하지 않습니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)