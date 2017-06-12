---

# required metadata
title: "Introduction to Microsoft R Server and R Client"
description: "Learn about Microsoft R features and components in R Server, R Client, R Open."
keywords: ""
author: "j-martens"
manager: "jhubbard"
ms.date: "05/10/2017"
ms.topic: "get-started-article"
ms.prod: "microsoft-r"
ms.service: ""
ms.assetid: ""

# optional metadata
ROBOTS: ""
audience: ""
ms.devlang: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.technology:
  - r-client
  - r-server
ms.custom: ""

---

# Microsoft R products and features

R is the world’s most powerful, and preferred, programming language for statistical computing, machine learning, and graphics. As an open source technology, R is supported by a thriving global community of users, developers, and contributors. Developers frequently provide tools incorporating their expertise in the form of R packages. Although R is widely used, deploying R in an enterprise setting has presented certain challenges, especially as the volume of data rises, or requirements for scale and support in production environments emerge.

Microsoft R fills the functional void in enterprise deployments by providing a collection of servers and tools that extend the capabilities of R. The Microsoft R product family builds on top of open source R, offering free and commercial products in the form of Microsoft R Server, Microsoft R Client, and Microsoft R Open. In addition to the over 8000 standard R packages available to all R users, Microsoft R Server and R Client include additional R packages and connectivity tools that enable remote compute context and remote execution, web service deployment, machine learning integration, and scalable solutions through clusters or parallelized workloads on platforms that support it.

<a name="compare-prods"></a>

## Compare products

The following table broadly compares members of the Microsoft R product family. All Microsoft R products are built on Microsoft R Open (MRO) and install the package automatically.

|Component  |Role |Price | Support | Intended use |
|-----------|-----|------|---------|--------------|
|[Microsoft R Open (MRO)](https://mran.microsoft.com/open/) | Microsoft's distribution of open source R | Free | Community forums <sup>1</sup>| Use MRO as you would any other distribution of R. Script written against MRO is straight R, composed of basic functions provided in publically available R packages.|
|[Microsoft R Client (MRC)](r-client.md) | Workstation version of Microsoft R | Free | Community forums <sup>1</sup>| Adds custom functionality provided in proprietary Microsoft R packages, intended for development and local execution of in-memory datasets.|
|[Microsoft R Server (MRS)](rserver.md) | Enterprise class server software | Commercial software | [Fully supported by Microsoft](rserver-servicing-support.md) | Adds custom functionality provided in proprietary Microsoft R packages, intended for local, remote, or distributed execution of larger datasets at scale.|

<sup>1</sup> Microsoft does not offer technical support for issues encountered in either MRO or MRC, but you can get peer support in [MSDN forums](https://social.msdn.microsoft.com/Forums/en-US/home?forum=ropen) and [StackOverflow](https://stackoverflow.com/questions/tagged/microsoft-r), to name a few.

## Compare features by product

Features provided by Microsoft R Server, Microsoft R Client, and Microsoft R Open can be categorized as shown in this table. This table slices key features by components. Additional capability provided in R Client and R Server is delivered via propertietary packages in Microsoft R.


<table>
    <thead>
        <tr>
            <th width=10%></th>
            <th width=23%>Microsoft R Open</th>
            <th width=32%>Microsoft R Client</th>
            <th width=35%>Microsoft R Server</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Storage</b></td>
            <td>Memory bound<sup>1</sup></td>
            <td>Memory bound<sup>1</sup> &amp; operates on large volumes when connected to R Server.</td>
            <td>Data chunking across multiple disks.<br />Operates on bigger volumes &amp; factors.</td>
        </tr>
        <tr>
            <td><b>Speed of Analysis</b></td>
            <td>Multithreaded via MKL<sup>2</sup> for non-RevoScaleR functions.</td>
            <td>Multithreaded via MKL<sup>2</sup> for non-RevoScaleR functions, but only up to 2 threads for ScaleR functions with a local compute context.</td>
            <td>Full parallel threading &amp; processing for RevoScaleR functions as well as for non-RevoScaleR functions (via MKL<sup>2</sup>) in both local and remote compute contexts.</td>
        </tr>
        <tr>
            <td><b>Analytic Breadth &amp; Depth</b></td>
            <td>Open source packages only.</td>
            <td>Open source R packages plus proprietary packages.</td>
            <td>Open source R packages plus proprietary packages with support for parallelization and distributed workloads.</td>
        </tr>
        <tr>
            <td><b><a href="operationalize/about.md">Operationalizing</a> R Analytics</b></td>
            <td>Not available</td>
            <td>Not available</td>
            <td>Includes the instant deployment and easy consumption of R analytics, interactive remote code execution, speedy realtime scoring, scalability, and enterprise-grade security.</td>
        </tr>
    </tbody>
</table>
<sup>1</sup> Memory bound because product can only process datasets that fit into the available memory.

<sup>2</sup> Because the Intel Math Kernel Library (MKL) is included in MRO, the performance of a generic R solution is generally better. MKL replaces the standard R implementations of Basic Linear Algebra Subroutines (BLAS) and the LAPACK library with multithreaded versions. As a result, calls to those low-level routines tend to execute faster on Microsoft R than on a conventional installation of R.

## Next Steps

If you are new to Microsoft R, we recommend starting with R Client and an integrated development environment like **R Tools for Visual Studio (RTVS)**. This configuration is free of charge. It gives you Microsoft R Open with full support of all base R functions so that you can write R-only solutions, but also includes the Microsoft R proprietary packages that run locally on your development computer.

Using just MRO and RTVS, you can use the R Core Team manuals that are part of every R distribution to learn how to code in R. Built-in manuals include *An Introduction to R*, *The R Language Definition*, *Writing R Extensions* and more. Beyond the standard R manuals, there are many other resources. [Learn about them here](microsoft-r-more-resources.md).

However, because you have R Client, your script can also include functions from Microsoft R packages, including MicrosoftML, olapR, and RevoScaleR. All of these packages are available in both R Client and R Server, but at different levels of capacity.

Tutorials in Microsoft R product documentation will help you learn how to use the functions in the proprietary packages:  

+ [Practice data import and exploration](scaler-getting-started-data-import-exploration.md)

+ [Explore R and ScaleR in 25 functions](microsoft-r-tutorial-R2RevoScaleR.md)

+ [Introduction to MicrosoftML](microsoftml-introduction.md)

## See Also

[What's new in R Server](rserver-whats-new.md)
