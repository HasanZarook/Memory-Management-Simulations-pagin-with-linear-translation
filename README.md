
# 🖥️ Memory Management Simulations

This repository contains Python scripts that simulate **classic memory management techniques** used in Operating Systems:

1. **Relocation with Base & Limit Registers**  
2. **Segmentation (two-segment model)**
you can find both 1 and 2 in my GitHub repo
3. **Paging with Linear Translation (Page Tables)**  

These scripts generate **virtual address traces** and demonstrate how addresses are translated into physical addresses (or flagged as invalid).

---

## 📂 Files
```

Memory-Management-Simulations/
│
├── relocation.py          # Relocation with base & limit registers
├── segmentation.py        # Segmentation with two segments
├── paging\_linear.py       # Paging with linear page table translation

````

---

## 🚀 Usage

### 1️⃣ Relocation (`relocation.py`)
Relocation uses **base + limit registers** for memory protection.  
👉 See detailed usage in that section above.

---

### 2️⃣ Segmentation (`segmentation.py`)
Segmentation splits the process into **two logical segments** (grows + and -).  
👉 See detailed usage in that section above.

---

### 3️⃣ Paging with Linear Translation (`paging_linear.py`)
Paging divides both **virtual and physical memory** into fixed-size **pages** and translates virtual addresses using a **page table**.

#### Example:
```bash
python paging_linear.py -s 1 -a 16k -p 64k -P 4k -n 5 -c
````

#### Options:

* `-s` : Random seed
* `-a` : Virtual address space size (e.g., 16k, 64k, 32m)
* `-p` : Physical memory size (must be > address space)
* `-P` : Page size (must be power of 2, e.g., 4k, 8k)
* `-n` : Number of virtual addresses to generate
* `-u` : Percentage of virtual space that is mapped (default 50%)
* `-A` : Comma-separated list of addresses instead of random
* `-v` : Verbose mode (shows VPN index with each page table entry)
* `-c` : Compute the physical addresses automatically

#### Sample Output:

```
Page Table (from entry 0 down to the max size)
   0x80000002
   0x80000003
   0x00000000
   0x80000005

Virtual Address Trace
  VA 0x00001234 (decimal:   4660) --> 00003234 (decimal  12852) [VPN 1]
  VA 0x0000abcd (decimal:  43981) -->  Invalid (VPN 2 not valid)
```

---

## 📊 Concepts Covered

* **Relocation** → Base & Limit registers
* **Segmentation** → Logical separation of address space
* **Paging** → Page tables, VPN, PFN, and offsets
* **Translation Lookups** → Virtual → Physical address mapping
* **Invalid Addresses** → Segmentation violations or unmapped pages

---

## 👨‍💻 Author

* Hasan Zarook (2021-CE-58)

---

