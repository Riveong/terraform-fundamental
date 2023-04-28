# terraform-fundamental
**Intermezzo**
To check if the terraform is installed you can check by using :

    terraform

if its installed then the output should be like :

    Usage: terraform [--version] [--help]  [args]
    The available commands for execution are listed below.
    The most common, useful commands are shown first, followed by
    less common or more advanced commands. If you're just getting
    started with Terraform, stick with the common commands. For the
    other commands, please read the help and docs before usage.
    Common commands:
        apply              Builds or changes infrastructure
        console            Interactive console for Terraform interpolations
        destroy            Destroy Terraform-managed infrastructure
        env                Workspace management
        fmt                Rewrites config files to canonical format
        get                Download and install modules for the configuration
        graph              Create a visual graph of Terraform resources
        import             Import existing infrastructure into Terraform
        init               Initialize a Terraform working directory
        output             Read an output from a state file
        plan               Generate and show an execution plan
        providers          Prints a tree of the providers used in the configuration
        push               Upload this Terraform module to Atlas to run
        refresh            Update local state file against real resources
        show               Inspect Terraform state or plan
        taint              Manually mark a resource for recreation
        untaint            Manually unmark a resource as tainted
        validate           Validates the Terraform files
        version            Prints the Terraform version
        workspace          Workspace management
    All other commands:
        debug              Debug output management (experimental)
        force-unlock       Manually unlock the terraform state
        state              Advanced state management

**Making the .tf file**
to build an compute instance first you need to make a file .tf in this case we will be making instance.tf file

    resource "google_compute_instance" "terraform" {
      project      = "<PROJECT_ID>"
      name         = "<NAME>"
      machine_type = "<MACHINE_TYPE>"
      zone         = "<ZONE>"
      boot_disk {
        initialize_params {
          image = "<IMAGE>"
        }
      }
      network_interface {
        network = "default"
        access_config {
        }
      }
    }
in this file you have to modify the values. for the example you can access instance.tf
or the [documentation](https://cloud.google.com/docs/terraform)

**Initialization**
after that the last thing we want do is to init the terraform

    terraform init
after that we can plan or just apply

    terraform plan
    terraform apply
if prompted: type yes then enter
after that an instance will be created
to show the terraform you can use:

    terraform show
