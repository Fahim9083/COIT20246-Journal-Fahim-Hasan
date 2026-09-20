## Task 1: Complete the Knowledge Test
![Knowledge Test](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/week8task1.png)

## Task 2: Login to Microsoft Learn on Demand 
**Completed**

## Task 3: Create an Azure Resource

During this module, I set up the following Azure resources:

- **Resource Group:** This acts as a logical container that groups related Azure solutions together. It simplifies management, monitoring, and billing by allowing me to treat a collection of resources as a single unit.
  ![RG](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/week8task3resource_group_creation.png)
- **Storage Account (`stgpstaticsite65293339`):** This resource provides a unique namespace in Azure for storing and accessing data objects. In this lab, I used it to host a static website by activating the built-in "Static Website" option. This automatically created a special `$web` container and provided a public endpoint URL to serve the web pages.
  ![SA](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/week8task3storage_accounts_creation.png)
  ![SA_2](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/week8task3storage_accounts_creation_successfull.png)

## Task 4: Create an Azure Virtual Machine and Allow Web Access

**1. VM Creation and Commands:**
I deployed an Ubuntu virtual machine through the Skillable lab (AZ900-011). The updated lab used the Azure Portal GUI rather than the CLI, so I have recorded the equivalent `az` commands below, which would produce the same result and install Nginx:

```bash
# 1. Create a resource group
az group create --name myResourceGroup --location australiaeast

# 2. Create the Virtual Machine
az vm create \
  --resource-group myResourceGroup \
  --name myVM \
  --image Ubuntu2204 \
  --admin-username azureuser \
  --generate-ssh-keys

# 3. Open port 80 to allow web traffic
az vm open-port --port 80 --resource-group myResourceGroup --name myVM

# 4. SSH into the VM
ssh -l azureuser <public-ip-address>

# 5. Install Nginx (inside the SSH session)
sudo apt-get update
sudo apt-get install -y nginx

# 6. Edit the web page (inside the SSH session)
sudo nano /var/www/html/index.html
```

**2. Public IP Address / Access URL:**
Because the lab environment did not support SSH editing, I used the Static Website feature from my Storage Account to demonstrate a working web endpoint. The public URL for my website is: 
`https://stgpstaticsite65293339.z13.web.core.windows.net/`

**3. Website Screenshot:**
![My website](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/static_website_update_with_name.png)

**4. Network Security Group (NSG) Rules:**
Two NSG rules control access to the VM:
1.  **Port 22 (SSH):** Enables Secure Shell access, allowing me to log in remotely to manage the server and install software such as Nginx.
2.  **Port 80 (HTTP):** Enables standard web traffic so that browsers can reach the web server and display the hosted site.

## Task 5: Compare Cloud vs On-Premise Costs

**1. Specifications and Cost Table**
*Note: The limits given by my tutor were: RAM between 8GB and 32GB, CPU 4 cores.*

| Specification | Consumer Desktop PC (Mwave) | Azure Cloud VM (Azure Pricing Calculator) |
| :--- | :--- | :--- |
| **Model / Size** | MSI PRO DP80 SFF Business Desktop | Standard_D4s_v4 (4 vCPUs, 16 GB RAM) |
| **CPU** | Intel Core i5-14400 (6 cores) | 4 vCPUs |
| **RAM** | 16 GB | 16 GB |
| **Storage** | 1 TB SSD | 0 GB Temporary Storage |
| **Operating System** | Windows 11 Pro (included) | Linux (Ubuntu) |
| **Region** | N/A (physical) | Australia East |
| **Upfront Cost (AUD)** | $1,399.00 | $0.00 |
| **Monthly Running Cost** | $0 (electricity ~$15/mo) | $175.20 |
| **Total Cost (1 Year)** | ~$1,579.00 | ~$2,102.40 |
| **Total Cost (3 Years)** | ~$1,939.00 | ~$6,307.20 |

![Local PC](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/local_pc.png)
![Virtual Machine](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/vm.png)

**2. Discussion of Trade-offs**
The desktop PC represents a **Capital Expenditure (CapEx)** approach. It requires a significant upfront investment of $1,399 AUD, but the ongoing operational costs are very low. Over a 3-year period, the total cost of ownership is roughly $1,939 AUD, making it considerably cheaper in the long run. However, it is a fixed asset that depreciates, requires physical maintenance, and cannot easily be scaled if business needs change.

The Azure Cloud VM follows an **Operational Expenditure (OpEx)** model. It has zero upfront cost, making it attractive for startups or short-term projects. However, the monthly running cost of $175.20 AUD means that over 3 years, the total cost reaches approximately $6,307 AUD—more than three times the cost of the desktop PC. The advantages of the cloud VM include scalability (I can resize it at any time), no physical maintenance, and the ability to delete it at any time to immediately stop paying. 

In summary, for a stable, long-term workload with predictable demand, the on-premise desktop PC is far more cost-effective. For short-term projects or situations where capital expenditure is difficult, the cloud VM offers valuable flexibility despite its higher total cost over time.


## Task 6: Create a Storage Blob in Azure

**1. Image URL and Screenshot:**
I uploaded an image to my Storage Account. I set the container's anonymous access level to "Blob" so it could be viewed publicly. 

![Blob Loading](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/blob-loading.png)

**2. Azure Portal Resources Screenshot:**
![Blob upload](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/blob_upload.png)

**Explanation:** 
A Blob container is used to store unstructured data (like images, videos, and documents). Setting the access level to "Blob" means that anyone who has the exact URL can view the file, but they cannot list or browse other files in the container. This is useful for hosting public assets like website images.

## Task 7: Create a Resource Lock

**Difference between a Read-only lock and a Delete lock:**

*   **Read-only lock:** This lock prevents users from modifying or deleting a resource. Users can still view the resource, but they cannot make any changes to its settings or configuration. This is useful for protecting critical resources that should never be altered.
*   **Delete lock:** This lock prevents users from deleting a resource. However, users are still allowed to modify and view the resource. This is useful for preventing accidental deletion of a resource that might still need to be updated or maintained.
    ![Local Creation](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/locks.png)
    ![Delete Lock Prevention](https://github.com/Fahim9083/COIT20246-Journal-Fahim-Hasan/blob/main/images/week8/delete-lock-working.png)
