<<<<<<< HEAD
# SUnv-Mol.Vw-API
Advanced Molecular Visualization API for PDB and AlphaFold Structures. It is primarily meant for educational purposes.
[README.md](https://github.com/user-attachments/files/23130974/README.md)
=======
# SUnv-Mol.Vw API
>>>>>>> ae45a21 (Initial commit: SUnv-Mol.Vw API v1.0)

A powerful, web-based molecular visualization API that provides interactive 3D visualization of protein structures from PDB and AlphaFold databases. Built with 3Dmol.js, this tool offers seamless integration into web applications and research workflows.

## 🧬 Features

### **Core Visualization**
- **3D Molecular Rendering**: High-quality 3D visualization using WebGL
- **Multiple Representations**: Cartoon, Stick, Line, Sphere, and Surface rendering
- **Dynamic Color Schemes**: Secondary Structure, Element, Chain, and pLDDT coloring
- **Interactive Controls**: Zoom, pan, rotate with mouse/touch support

### **Data Sources**
- **PDB Structures**: Direct integration with RCSB PDB database
- **AlphaFold Models**: Support for AI-predicted protein structures
- **Large Structure Support**: Automatic fallback to mmCIF format for large macromolecular complexes
- **Automatic Detection**: Smart input parsing for PDB IDs and AlphaFold identifiers

### **Advanced Features**
- **Chain Management**: Multi-chain structure support with individual chain toggling
- **Single Chain Optimization**: Specialized handling for single-chain structures
- **Surface Rendering**: Molecular surface visualization with water inclusion/exclusion
- **Atom Picking**: Click-to-label functionality for residue identification
- **Confidence Visualization**: pLDDT confidence scores for AlphaFold structures
- **Responsive Design**: Optimized for desktop and mobile devices
- **Scrollable Controls**: Auto-scrolling control panel for better usability

### **API Integration**
- **URL Parameters**: Simple integration via URL parameters
- **Embeddable**: Easy embedding in web pages and applications
- **RESTful**: Clean API endpoints for programmatic access

## 🚀 Quick Start

### **Basic Usage**

Simply open the API viewer with a structure ID:

```
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=1CRN
```

### **Supported Structure IDs**

**PDB Structures**:
```
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=1CRN
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=4DFR
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=1ATJ
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=4V6X
```

**AlphaFold Structures**:
```
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=AF-Q9I4X8-F1
https://your-domain.com/SUnv-Mol_Vw_api.html?entId=AF-P12345-F1
```

### **URL Parameters**

| Parameter | Description | Example | Required |
|-----------|-------------|---------|----------|
| `entId` | Structure identifier (PDB ID or AlphaFold ID) | `1CRN`, `AF-Q9I4X8-F1` | Yes |
| `pdbid` | Alternative parameter name | `1CRN` | No |
| `pdbId` | Alternative parameter name | `1CRN` | No |
| `id` | Alternative parameter name | `1CRN` | No |

## 📖 Documentation

### **API Endpoints**

#### **Main Viewer**
- **File**: `SUnv-Mol_Vw_api.html`
- **Purpose**: Full-featured molecular viewer
- **Features**: All visualization options, controls, and interactions

#### **Embeddable Version**
- **File**: `SUnv-Mol_Vw_api.html`
- **Purpose**: Lightweight embeddable viewer
- **Features**: Core visualization with minimal UI

### **Visualization Options**

#### **Representations**
- **Cartoon**: Protein secondary structure with arrows for β-sheets
- **Ball & Stick**: Bond representation with adjustable thickness
- **Wireframe**: Wireframe representation with proper thin lines
- **Sphere**: Van der Waals spheres with realistic atomic radii
- **Surface**: Molecular surface with adjustable opacity

#### **Color Schemes**
- **Secondary Structure**: Color-coded by α-helices, β-sheets, and loops
- **Element**: Color-coded by atomic element
- **Chain**: Color-coded by protein chain
- **pLDDT**: Confidence scores for AlphaFold structures (Very High, Confident, Low, Very Low). Color mode shown only when AlphaFold model is loaded.

#### **Surface Options**
- **None**: No surface rendering
- **Surface**: Full molecular surface including water molecules
- **Surface (-) Water**: Molecular surface excluding water molecules

### **Chain Management**

For multi-chain structures:
- **Default Display**: Only Chain A visible by default
- **Chain Selection**: Toggle individual chains on/off
- **Dynamic Filtering**: Real-time chain visibility updates
- **Center & Fit**: Centers only on visible chains

For single-chain structures:
- **Optimized Rendering**: Specialized handling for single-chain entries
- **Consistent Representation**: Proper representation modes without conflicts
- **Standard VDW Radii**: Correct sphere sizes for atomic visualization

### **Large Structure Support**

The API automatically handles large macromolecular complexes:
- **Automatic Fallback**: Tries PDB format first, then mmCIF format
- **Format Detection**: Automatically detects and uses the appropriate format
- **Seamless Loading**: No user intervention required for large structures
- **Examples**: Structures like 4V6X (Photosystem II) load automatically

### **Interactive Features**

#### **Mouse Controls**
- **Left Click + Drag**: Rotate structure
- **Right Click + Drag**: Pan/translate structure
- **Mouse Wheel**: Zoom in/out
- **Click on Atom**: Display residue information (Residue:Number:Chain)

#### **Keyboard Shortcuts**
- **Enter**: Load structure from input field
- **Escape**: Clear atom labels

## 🛠️ Technical Details

### **Dependencies**
- **3Dmol.js**: 3D molecular visualization library
- **html2canvas**: PNG export functionality
- **Modern Web Browser**: Chrome, Firefox, Safari, Edge (WebGL support required)

### **Browser Compatibility**
- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+

### **Performance**
- **Rendering**: Hardware-accelerated WebGL
- **Memory**: Optimized for structures up to 50,000 atoms
- **Loading**: Asynchronous structure loading with progress indicators
- **Large Structures**: Efficient handling of macromolecular complexes

### **File Formats**
- **Input**: PDB and mmCIF formats (automatic format detection)
- **Output**: PNG image export with structure information overlay

### **Recent Improvements**
- **Single Chain Optimization**: Fixed representation modes for single-chain structures
- **Sphere Representation**: Correct VDW radii for atomic spheres
- **Line Representation**: Proper thin line thickness
- **Large Structure Support**: Automatic mmCIF fallback for large complexes
- **Scrollable Controls**: Better UI for smaller screens
- **AlphaFold Defaults**: pLDDT coloring as default for AlphaFold structures

## 📊 Use Cases

### **Research Applications**
- **Protein Structure Analysis**: Visualize and analyze protein conformations
- **Drug Discovery**: Examine protein-ligand interactions
- **Structural Biology**: Compare different protein structures
- **Large Complex Studies**: Visualize macromolecular assemblies like ribosomes, photosystems
- **Education**: Interactive learning tool for molecular biology

### **Web Integration**
- **Research Websites**: Embed molecular viewers in research pages
- **Educational Platforms**: Interactive content for online courses
- **Database Interfaces**: Visualize structures from biological databases
- **Collaboration Tools**: Share and discuss molecular structures

## 🔧 Installation & Setup

### **Local Development**

1. **Clone Repository**:
   ```bash
   git clone https://github.com/rachedi-2526/SUnv-Mol.Vw-API.git
   cd SUnv-Mol.Vw-API
   ```

2. **Serve Files**:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Using PHP
   php -S localhost:8000
   ```

3. **Access Viewer**:
   ```
   http://localhost:8000/SUnv-Mol_Vw_api.html?entId=1CRN
   ```

### **Web Deployment**

#### **GitHub Pages**
1. Upload files to GitHub repository
2. Enable GitHub Pages in repository settings
3. Access via: `https://rachedi-2526.github.io/repository-name/`

#### **Netlify**
1. Connect GitHub repository to Netlify
2. Deploy automatically on code changes
3. Access via custom Netlify URL

#### **Traditional Web Hosting**
1. Upload files to web server
2. Ensure proper MIME types for HTML/CSS/JS
3. Access via domain URL

## 📝 Examples

### **Basic Integration**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Molecular Viewer Example</title>
</head>
<body>
    <h1>Molecular Structure Viewer</h1>
    
    <!-- Embed viewer -->
    <iframe 
        src="SUnv-Mol_Vw_api.html?entId=1CRN"
        width="800" 
        height="600"
        frameborder="0">
    </iframe>
    
    <!-- Direct link -->
    <p>
        <a href="SUnv-Mol_Vw_api.html?entId=1CRN" target="_blank">
            View 1CRN Structure
        </a>
    </p>
</body>
</html>
```

### **JavaScript Integration**

```javascript
// Load structure programmatically
function loadStructure(structureId) {
    const viewerUrl = `SUnv-Mol_Vw_api.html?entId=${structureId}`;
    window.open(viewerUrl, '_blank');
}

// Example usage
loadStructure('1CRN');        // PDB structure
loadStructure('AF-Q9I4X8-F1'); // AlphaFold structure
loadStructure('4V6X');        // Large macromolecular complex
```

### **URL Examples**

```javascript
// PDB Structures
const pdbExamples = [
    '1CRN',  // Crambin (small protein)
    '4DFR',  // Dihydrofolate reductase
    '1ATJ',  // Antithrombin
    '2POR',  // Porin
    '1HTM',  // Hemoglobin
    '4V6X'   // Photosystem II (large complex)
];

// AlphaFold Structures
const alphafoldExamples = [
    'AF-Q9I4X8-F1',  // HPt domain-containing protein
    'AF-P12345-F1',  // Example structure
    'AF-A0A0F7H7J7-F1' // Another example
];
```

## 🧪 Testing

### **Test Structures**

**PDB Test Cases**:
- `1CRN` - Small protein (46 residues)
- `4DFR` - Multi-chain complex
- `1ATJ` - Large protein with multiple chains
- `2POR` - Membrane protein
- `4V6X` - Large macromolecular complex (Photosystem II)

**AlphaFold Test Cases**:
- `AF-Q9I4X8-F1` - HPt domain-containing protein
- `AF-P12345-F1` - Example predicted structure

**Single Chain Test Cases**:
- `1CRN` - Single chain protein
- `1UBQ` - Ubiquitin (single chain)

### **Browser Testing**
- Test on multiple browsers and devices
- Verify WebGL support
- Check responsive design on mobile
- Test large structure loading

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### **Development Setup**
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### **Bug Reports**
Please report bugs via [GitHub Issues](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Dr. Abdelkrim RACHEDI** - *Initial work* - [University of Saida - Dr. Moulay Tahar, Saida, Algeria](https://univ-saida.dz)

## 🙏 Acknowledgments

- **3Dmol.js** - 3D molecular visualization library
- **RCSB PDB** - Protein Data Bank
- **AlphaFold Database** - AI-predicted protein structures
- **University of Saida** - Institutional support

## 📞 Support

- **Documentation**: [Wiki](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/wiki)
- **Issues**: [GitHub Issues](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues)
- **Email**: [bioinformatics@univ-saida.dz](mailto:bioinformatics@univ-saida.dz)

## 🔗 Links

- **Live Demo**: [https://rachedi-2526.github.io/SUnv-Mol.Vw-API/](https://rachedi-2526.github.io/SUnv-Mol.Vw-API/)
- **GitHub Repository**: [https://github.com/rachedi-2526/SUnv-Mol.Vw-API](https://github.com/rachedi-2526/SUnv-Mol.Vw-API)
- **Documentation**: [https://github.com/rachedi-2526/SUnv-Mol.Vw-API/wiki](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/wiki)

---

**© 2025 University of Saida - Dr. Moulay Tahar, Saida, Algeria**

<<<<<<< HEAD
*SUnv-Mol.Vw API - Advanced Molecular Visualization for Research and Education*
=======
*SUnv-Mol.Vw API - Advanced Molecular Visualization for Research and Education*
>>>>>>> ae45a21 (Initial commit: SUnv-Mol.Vw API v1.0)
