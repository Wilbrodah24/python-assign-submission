# python-assign-submission

def file_processor():
    # Get input filename from user
    input_filename = input("Enter the name of the file to read: ")
    output_filename = input("Enter the name of the output file: ")
    
    try:
        # Try to open and read the input file
        with open(input_filename, 'r') as input_file:
            content = input_file.read()
            
        # Modify the content (convert to uppercase in this example)
        modified_content = content.upper()
        
        # Write the modified content to the output file
        with open(output_filename, 'w') as output_file:
            output_file.write(modified_content)
            
        print(f"File processed successfully! Modified content written to {output_filename}")
    
    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    except PermissionError:
        print(f"Error: Permission denied when accessing '{input_filename}'.")
    except IOError as e:
        print(f"An error occurred while processing the file: {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

 Run the program
if __name__ == "__main__":
    file_processor()
