# Active Directory
<h2>Description</h2>
Let's take alook at some of concepts of Active Directory and how they apply or don't apply to Azure AD. I'll also deploy and configure Active Directory domain services on-premises before we connect our on-premises deployment to Azure in the next module. 
<br />
<h3>First, let's have a review of these two technologies</h3>
<img src="https://i.imgur.com/AChhngY.jpeg" height="80%" width="80%" alt="Active Directory"/>
<br />
<p>Active Directory was introduced in Windows Server 2000 as a centralized directory service for storing information about users and groups, as well as other resources on the network, like servers, desktops, file shares, and printers. Active Directory is made up of a few different services, but when I talk about AD, I'm generally talking about Active Directory domain services, and that's what I'll be referring to in this example. I'll also touch on Active Directory federation services, as it provides authentication services for applications and enables users outside your network to access those applications. But AD domain services is the core of any Windows-based network. It stores data about users and resources, and it provides a way for computers on the network to find and access that data. Active Directory is involved in authentication and authorization.</p>
<img src="https://i.imgur.com/GC9bDcY.jpeg" height="80%" width="80%" alt="Active Directory"/>
<br />
<p>When a user logs on, they verify their identity, and when their device tries to access a resource on the network, Active Directory is used to grant Kerberos tickets to authorize that access. So that's something fundamental to Active Directory, that in terms of authentication and authorization, it uses a protocol called Kerberos. It can also use an older protocol called NTLM, which stands for NT Land Manager. Those protocols require that certain ports be open on the network, and all the users, computers, and resources be registered with that central authority.There are ways to trust outside networks and organizations using Active Directory federation services, and we'll get into that, but for the most part, you require line of sight to domain controllers to make things work, meaning everything is located on the same network.</p>
<img src="https://i.imgur.com/J0ncoeA.jpeg" height="80%" width="80%" alt="Active Directory"/>
<br />
<p></p>The cloud was built differently. Things are accessed over the internet, so the only ports that can really be relied upon to be open are 443 for secure communication and port 80 for basic HTTP traffic. With all the applications on the internet, you don't want to have to have separate passwords everywhere, so the web introduced protocols for allowing user identities to be validated by other identity providers to access resources through consent.</p>
<img src="https://i.imgur.com/bKmkxV4.jpeg" height="80%" width="80%" alt="Active Directory"/>
<br /><p>You see this when you log into a website using your Gmail or Facebook or Microsoft ID, and you have to grant permission. The protocols underlying that are OAuth 2.0 and OpenID Connect, which are different than Kerberos and NTLM. Azure Active Directory was built to use these newer protocols and to grant access to resources running in the cloud. Azure AD can actually use Kerberos in certain situations, though, and we'll discuss that later.</p>
